# Test Plan for Edge Devices - Windows 10 (私家版) 

パートナー様向け手順書の Step 5 までが完了した状態を想定しています。

## Step 1 – 環境情報の取得  

1. IoT Edge version の取得
    ```powershell
    iotedge --version
    ```
    **PowerShell プロンプトのスクリーンショットを取得してください。**  

2. Architecture の取得（オプション）
    ```powershell
    (Get-Process -Id $PID).StartInfo.EnvironmentVariables["PROCESSOR_ARCHITECTURE"]
    ```
    **PowerShell プロンプトのスクリーンショットを取得してください。**  

3. IoT Edge サービス状況 の取得
    ```powershell
    Get-Service iotedge  
    ```
    **PowerShell プロンプトのスクリーンショットを取得してください。**

4. IoT Edge モジュールリスト の取得
    ```powershell
    iotedge list
    ```
    **PowerShell プロンプトのスクリーンショットを取得してください。**    

## Step 2 – Edge モジュール デプロイ確認  
モジュールのデプロイを行いますので、操作可能な IoT Hub に接続し直す必要があります。  
Connection String の変更は **C:\ProgramData\iotedge\config.yaml** を編集し、iotedge をリスタートします。  
    
> Stop-Service iotedge -NoWait  
> sleep 5  
> Start-Service iotedge  

1. **Simulated Temperature** モジュール の デプロイ

    Azure ポータルを用いるか、または [deploymentmanifest.json]() をダウンロードし、ConnectionString を編集後、VSCode を用いて該当 IoT Edge デバイスにデプロイします。

2. IoT Edge モジュールリスト の取得（モジュールが正しくデプロイされていることを確認）
    ```powershell
    iotedge list
    ```
    **PowerShell プロンプトのスクリーンショットを取得してください。**   

2. Simulated Temperature モジュール のログを取得（モジュールが正しく動作していることを確認）
    ```powershell
    iotedge logs simulatedtemperature --tail 100
    ```
    **PowerShell プロンプトのスクリーンショットを取得してください。**   

## Step 3 – パートナー様インストラクション の確認


以上ステップを完了されましたら、メールにてご連絡ください。


