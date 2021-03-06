---
title: プライバシー プロンプトを使用してカスタム ブートストラップを作成する
description: 新しいファイルバージョンとアセンブリバージョンを持つアセンブリが使用可能になったときに自動的に更新されるように ClickOnce アプリケーションを構成する方法について説明します。
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, prerequisites
- dependencies [.NET Framework], custom bootstrapper package
- deploying applications [Visual Studio], custom prerequisites
- Windows Installer deployment, prerequisites
- prerequisites [.NET Framework], custom bootstrapper package
ms.assetid: 2f3edd6a-84d1-4864-a1ae-6a13c5732aae
author: mikejo5000
ms.author: mikejo
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: b2f36ee884beb3b79244e4621ba305c06aafe8ff
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99915758"
---
# <a name="walkthrough-create-a-custom-bootstrapper-with-a-privacy-prompt"></a>チュートリアル: プライバシー プロンプトを使用してカスタム ブートストラップを作成する
新しいファイルバージョンとアセンブリバージョンを持つアセンブリが使用可能になると、ClickOnce アプリケーションを自動的に更新するように構成できます。 お客様がこの動作に同意したことを確認するために、プライバシーに関するプロンプトを表示することができます。 次に、アプリケーションに対してアクセス許可を自動的に更新するかどうかを選択できます。 アプリケーションの自動更新が許可されていない場合は、インストールされません。

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

## <a name="prerequisites"></a>必須コンポーネント
 このチュートリアルを実行するには、次のコンポーネントが必要です。

- Visual Studio 2010。

## <a name="create-an-update-consent-dialog-box"></a>[更新プログラムの同意を作成する] ダイアログボックス
 プライバシープロンプトを表示するには、アプリケーションの自動更新に同意するようにリーダーに要求するアプリケーションを作成します。

#### <a name="to-create-a-consent-dialog-box"></a>同意ダイアログボックスを作成するには

1. **[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。

2. [ **新しいプロジェクト** ] ダイアログボックスで、[ **Windows**] をクリックし、[ **windowsフォームアプリケーション**] をクリックします。

3. [ **名前**] に「 **conのダイアログ**」と入力し、[ **OK**] をクリックします。

4. デザイナーで、フォームをクリックします。

5. [ **プロパティ** ] ウィンドウで、 **Text** プロパティを [ **Update 同意] ダイアログボックス** に変更します。

6. [ **ツールボックス**] で [ **すべての Windows フォーム**] を展開し、[ **ラベル** ] コントロールをフォームにドラッグします。

7. デザイナーで、[ラベル] コントロールをクリックします。

8. [**プロパティ**] ウィンドウで、[**外観**] の下の **Text** プロパティを次のように変更します。

    インストールしようとしているアプリケーションで、Web 上の最新の更新プログラムが確認されます。 [同意する] をクリックすると、アプリケーションがインターネットから更新プログラムを自動的にチェックしてインストールすることを承認します。

9. **ツールボックス** で、 **Checkbox** コントロールをフォームの中央にドラッグします。

10. [**プロパティ**] ウィンドウで、[**レイアウト**] の [ **Text** ] プロパティを [**同意** する] に変更します。

11. [ **ツールボックス**] で、 **ボタン** コントロールをフォームの左下にドラッグします。

12. [**プロパティ**] ウィンドウで、[**レイアウト**] の [ **Text** ] プロパティを変更して **続行** します。

13. [**プロパティ**] ウィンドウで、[**デザイン**] の下の **(Name)** プロパティを **ProceedButton** に変更します。

14. [ **ツールボックス**] で、 **ボタン** コントロールをフォームの右下にドラッグします。

15. [**プロパティ**] ウィンドウで、[**レイアウト**] の [ **Text** ] プロパティを「 **Cancel**」に変更します。

16. [**プロパティ**] ウィンドウで、[**デザイン**] の [ **(名前)** ] プロパティを [**キャンセル]** に変更します。

17. デザイナーで、[ **同意** する] チェックボックスをダブルクリックして、CheckedChanged イベントハンドラーを生成します。

18. Form1 コードファイルで、CheckedChanged イベントハンドラーに次のコードを追加します。

     [!code-csharp[ConsentDialog#1](../deployment/codesnippet/CSharp/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_1.cs)]
     [!code-vb[ConsentDialog#1](../deployment/codesnippet/VisualBasic/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_1.vb)]

19. クラスコンストラクターを更新して、既定で [ **続行** ] ボタンを無効にします。

     [!code-csharp[ConsentDialog#6](../deployment/codesnippet/CSharp/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_2.cs)]
     [!code-vb[ConsentDialog#6](../deployment/codesnippet/VisualBasic/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_2.vb)]

20. Form1 コードファイルで、ブール変数の次のコードを追加して、エンドユーザーがオンライン更新を同意したかどうかを追跡します。

     [!code-csharp[ConsentDialog#3](../deployment/codesnippet/CSharp/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_3.cs)]
     [!code-vb[ConsentDialog#3](../deployment/codesnippet/VisualBasic/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_3.vb)]

21. デザイナーで、[ **続行** ] ボタンをダブルクリックして、click イベントハンドラーを生成します。

22. Form1 コードファイルで、[ **続行** ] ボタンの click イベントハンドラーに次のコードを追加します。

     [!code-csharp[ConsentDialog#2](../deployment/codesnippet/CSharp/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_4.cs)]
     [!code-vb[ConsentDialog#2](../deployment/codesnippet/VisualBasic/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_4.vb)]

23. デザイナーで、[ **キャンセル** ] ボタンをダブルクリックして、クリックイベントハンドラーを生成します。

24. Form1 コードファイルで、[ **キャンセル** ] ボタンの click イベントハンドラーに次のコードを追加します。

     [!code-csharp[ConsentDialog#4](../deployment/codesnippet/CSharp/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_5.cs)]
     [!code-vb[ConsentDialog#4](../deployment/codesnippet/VisualBasic/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_5.vb)]

25. エンドユーザーがオンライン更新に同意しない場合にエラーが返されるように、アプリケーションを更新します。

     Visual Basic 開発者のみ:

    1. **ソリューションエクスプローラー** で、[ **con] ダイアログボックス** をクリックします。

    2. [ **プロジェクト** ] メニューの [ **モジュールの追加**] をクリックし、[ **追加**] をクリックします。

    3. Module1.vb コードファイルで、次のコードを追加 *します。*

        [!code-vb[ConsentDialog#7](../deployment/codesnippet/VisualBasic/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_6.vb)]

    4. [ **プロジェクト** ] メニューの [ **Conのプロパティ]** をクリックし、[ **アプリケーション** ] タブをクリックします。

    5. **アプリケーションフレームワークを有効にする**] チェックボックスをオフにします。

    6. [ **スタートアップオブジェクト** ] ドロップダウンメニューで、[ **Module1**] を選択します。

       > [!NOTE]
       > アプリケーションフレームワークを無効にすると、Windows XP の visual スタイル、アプリケーションイベント、スプラッシュスクリーン、単一インスタンスアプリケーションなどの機能が無効になります。 詳細については、「[[アプリケーション] ページ (プロジェクト デザイナー) (Visual Basic)](../ide/reference/application-page-project-designer-visual-basic.md)」を参照してください。

       Visual C# の開発者のみ:

       *Program.cs* コードファイルを開き、次のコードを追加します。

       [!code-csharp[ConsentDialog#5](../deployment/codesnippet/CSharp/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_7.cs)]

26. [ **ビルド** ] メニューの [ **buildsolution**] をクリックします。

## <a name="create-the-custom-bootstrapper-package"></a>カスタムブートストラップパッケージを作成する
 エンドユーザーにプライバシーに関する確認メッセージを表示するには、[更新プログラムの同意] ダイアログアプリケーション用のカスタムブートストラップパッケージを作成し、すべての ClickOnce アプリケーションに前提条件として含めることができます。

 この手順では、次のドキュメントを作成してカスタムブートストラップパッケージを作成する方法を示します。

- ブートストラップの内容を記述する *product.xml* マニフェストファイル。

- 文字列やソフトウェアライセンス条項など、パッケージのローカライズ固有の側面を一覧表示する *package.xml* マニフェストファイル。

- ソフトウェアライセンス条項のドキュメント。

#### <a name="step-1-to-create-the-bootstrapper-directory"></a>手順 1: ブートストラップディレクトリを作成するには

1. *%PROGRAMFILES%\Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages* に、 **updatecon** という名前のディレクトリを作成します。

    > [!NOTE]
    > このフォルダーを作成するには、管理者特権が必要な場合があります。

2. [ *Updatecon] ダイアログ* ディレクトリで、 *en* という名前のサブディレクトリを作成します。

    > [!NOTE]
    > ロケールごとに新しいディレクトリを作成します。 たとえば、fr および de ロケールのサブディレクトリを追加できます。 これらのディレクトリには、必要に応じて、フランス語およびドイツ語の文字列と言語パックが含まれます。

#### <a name="step-2-to-create-the-productxml-manifest-file"></a>手順 2: product.xml マニフェストファイルを作成する

1. *product.xml* という名前のテキストファイルを作成します。

2. *product.xml* ファイルで、次の XML コードを追加します。 既存の XML コードを上書きしないようにしてください。

    ```xml
    <Product
      xmlns="http://schemas.microsoft.com/developer/2004/01/bootstrapper"
      ProductCode="Microsoft.Sample.EULA">
      <!-- Defines the list of files to be copied on build. -->
      <PackageFiles CopyAllPackageFiles="false">
        <PackageFile Name="ConsentDialog.exe"/>
      </PackageFiles>

      <!-- Defines how to run the Setup package.-->
      <Commands >
        <Command PackageFile = "ConsentDialog.exe" Arguments=''>
          <ExitCodes>
            <ExitCode Value="0" Result="Success" />
            <ExitCode Value="-1" Result="Fail" String="AU_Unaccepted" />
            <DefaultExitCode Result="Fail"
              FormatMessageFromSystem="true" String="GeneralFailure" />
          </ExitCodes>
        </Command>
      </Commands>

    </Product>
    ```

3. ファイルを Updateconのダイアログブートストラップディレクトリに保存します。

#### <a name="step-3-to-create-the-packagexml-manifest-file-and-the-software-license-terms"></a>手順 3: package.xml マニフェストファイルとソフトウェアライセンス条項を作成するには

1. *package.xml* という名前のテキストファイルを作成します。

2. *package.xml* ファイルで、次の XML コードを追加してロケールを定義し、ソフトウェアライセンス条項を含めます。 既存の XML コードを上書きしないようにしてください。

    ```xml
    <Package
      xmlns="http://schemas.microsoft.com/developer/2004/01/bootstrapper"
      Name="DisplayName"
      Culture="Culture"
      LicenseAgreement="eula.rtf">
      <PackageFiles>
        <PackageFile Name="eula.rtf"/>
      </PackageFiles>

      <!-- Defines a localizable string table for error messages. -->
      <Strings>
        <String Name="DisplayName">Update Consent Dialog</String>
        <String Name="Culture">en</String>
        <String Name="AU_Unaccepted">The automatic update agreement is not accepted.</String>
        <String Name="GeneralFailure">A failure occurred attempting to launch the setup.</String>
      </Strings>
    </Package>
    ```

3. UpdateConsentDialog ブートストラップディレクトリの en サブディレクトリにファイルを保存します。

4. ソフトウェアライセンス条項として、「 *eula* 」という名前のドキュメントを作成します。

    > [!NOTE]
    > ソフトウェアライセンス条項には、ライセンス、保証、負債、および地方法に関する情報が含まれている必要があります。 これらのファイルはロケール固有である必要があるため、MBCS または UNICODE 文字をサポートする形式でファイルが保存されていることを確認してください。 ソフトウェアライセンス条項の内容については、法務部門に問い合わせてください。

5. *Updateconsentdialog* ブートストラップディレクトリの en サブディレクトリにドキュメントを保存します。

6. 必要に応じて、新しい *package.xml* マニフェストファイルを作成し、各ロケールのソフトウェアライセンス条項用の新しい *eula .rtf* ドキュメントを作成します。 たとえば、fr および de ロケール用のサブディレクトリを作成した場合は、個別の package.xml マニフェストファイルとソフトウェアライセンス条項を作成し、fr サブディレクトリと de サブディレクトリに保存します。

## <a name="set-the-update-consent-application-as-a-prerequisite"></a>更新プログラムの同意アプリケーションを前提条件として設定する
 Visual Studio では、更新プログラムの同意アプリケーションを前提条件として設定できます。

#### <a name="to-set-the-update-consent-application-as-a-prerequisite"></a>更新プログラムの同意アプリケーションを前提条件として設定するには

1. [ **ソリューションエクスプローラー** で、デプロイするアプリケーションの名前をクリックします。

2. **[プロジェクト]** メニューの *ProjectName の* **[プロパティ]** をクリックします。

3. [ **発行** ] ページをクリックし、[ **必須コンポーネント**] をクリックします。

4. **更新プログラムの同意ダイアログ** を選択します。

    > [!NOTE]
    > [必須コンポーネント] ダイアログボックスの [更新プログラムの同意] ダイアログを表示するには、Visual Studio を閉じてから再度開く必要があります。

5. **[OK]** をクリックします。

## <a name="create-and-test-the-setup-program"></a>セットアッププログラムを作成してテストする
 更新プログラムの同意アプリケーションを前提条件として設定した後、アプリケーションのインストーラーとブートストラップを生成することができます。

#### <a name="to-create-and-test-the-setup-program-by-not-clicking-i-agree"></a>[同意しない] をクリックしてセットアッププログラムを作成およびテストするには

1. [ **ソリューションエクスプローラー** で、デプロイするアプリケーションの名前をクリックします。

2. **[プロジェクト]** メニューの *ProjectName の* **[プロパティ]** をクリックします。

3. [ **発行** ] ページをクリックし、[ **今すぐ発行**] をクリックします。

4. 発行の出力が自動的に開かない場合は、発行の出力に移動します。

5. *Setup.exe* プログラムを実行します。

     セットアッププログラムでは、[同意の更新] ダイアログソフトウェアの使用許諾契約書が表示されます。

6. ソフトウェア使用許諾契約書を読み、[ **同意** する] をクリックします。

     更新プログラムの同意ダイアログアプリケーションが表示され、次のテキストが表示されます。インストールしようとしているアプリケーションによって、Web 上の最新の更新プログラムがチェックされます。 [同意する] をクリックすると、インターネット上で自動的に更新プログラムを確認するようにアプリケーションを承認します。

7. アプリケーションを閉じるか、[キャンセル] をクリックします。

     アプリケーションでエラーが発生しました。 *ApplicationName* 用のシステムコンポーネントのインストール中にエラーが発生しました。 すべてのシステムコンポーネントが正常にインストールされるまで、セットアップを続行できません。

8. [詳細] をクリックすると、次のエラーメッセージが表示されます: "コンポーネントの更新の同意ダイアログがインストールに失敗しました。" 自動更新契約は受け入れられません。 "というエラーメッセージが表示されます。 次のコンポーネントのインストールに失敗しました:-更新プログラムの同意ダイアログ

9. **[閉じる]** をクリックします。

#### <a name="to-create-and-test-the-setup-program-by-clicking-i-agree"></a>[同意する] をクリックしてセットアッププログラムを作成およびテストするには

1. [ **ソリューションエクスプローラー** で、デプロイするアプリケーションの名前をクリックします。

2. **[プロジェクト]** メニューの *ProjectName の* **[プロパティ]** をクリックします。

3. [ **発行** ] ページをクリックし、[ **今すぐ発行**] をクリックします。

4. 発行の出力が自動的に開かない場合は、発行の出力に移動します。

5. *Setup.exe* プログラムを実行します。

     セットアッププログラムでは、[同意の更新] ダイアログソフトウェアの使用許諾契約書が表示されます。

6. ソフトウェア使用許諾契約書を読み、[ **同意** する] をクリックします。

     更新プログラムの同意ダイアログアプリケーションが表示され、次のテキストが表示されます。インストールしようとしているアプリケーションによって、Web 上の最新の更新プログラムがチェックされます。 [同意する] をクリックすると、インターネット上で自動的に更新プログラムを確認するようにアプリケーションを承認します。

7. [ **同意** する] をクリックし、[ **続行**] をクリックします。

     アプリケーションのインストールが開始されます。

8. [アプリケーションのインストール] ダイアログボックスが表示されたら、[ **インストール**] をクリックします。

## <a name="see-also"></a>関連項目
- [アプリケーション配置の必要条件](../deployment/application-deployment-prerequisites.md)
- [ブートストラップ パッケージの作成](../deployment/creating-bootstrapper-packages.md)
- [方法: 製品マニフェストを作成する](../deployment/how-to-create-a-product-manifest.md)
- [方法: パッケージ マニフェストを作成する](../deployment/how-to-create-a-package-manifest.md)
- [製品およびパッケージスキーマリファレンス](../deployment/product-and-package-schema-reference.md)