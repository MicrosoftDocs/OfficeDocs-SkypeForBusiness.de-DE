---
title: "Zuweisen eines Drittanbieters für Audiokonferenzen"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/22/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.lync.lac.DialInExportImport
- ms.lync.lac.DialInProvider
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- Strat_SB_PSTN
ms.assetid: 77f68ca7-c1cf-40d9-9c23-87a6b2abe9de
description: "Learn how to set up a third-party as your dial-in conferencing provider with Skype for Business. "
---

# Zuweisen eines Drittanbieters für Audiokonferenzen

Ein Audiokonferenzanbieter stellt die  *Konferenzbrücke*  bereit. Über die Konferenzbrücke werden Einwahltelefonnummern, PINs und Konferenzkennungen für die erstellten Besprechungen bereitgestellt. Sie müssen nur den Mitarbeitern, die Skype for Business- oder Microsoft Teams-Besprechungen planen oder leiten werden, einen Audiokonferenzanbieter zuweisen.
  
> [!NOTE]
> Für Microsoft Teams können Benutzer keinen Drittanbieter für Audiokonferenzen verwenden, sie müssen Audiokonferenzen in Office 365 verwenden. Dadurch wird Microsoft als Audiokonferenzanbieter festgelegt. 
  
## Schritte VOR dem Zuweisen eines Drittanbieters für Audiokonferenzen

1. Je nach Ihrem Office 365-Plan müssen Sie möglicherweise Add-On-Lizenzen für **Audiokonferenzen** für die Mitarbeiter in Ihrer Organisation erwerben, die Skype for Business- oder Microsoft Teams-Besprechungen mit Audiokonferenzen planen oder leiten werden. Weitere Informationen finden Sie unter[Add-On-Lizenzierung für Skype for Business und Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
2. Wenn Sie Add-On-Lizenzen für **Audiokonferenzen** erworben haben, weisen Sie diese den Mitarbeitern in Ihrer Organisation zu, die Besprechungen mit Audiokonferenzen planen oder leiten werden. Weitere Informationen finden Sie unter[Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).
    
    > [!NOTE]
    > Wenn Sie einem Benutzer eine Lizenz für **Audiokonferenzen** zuweisen, **NACHDEM** Sie ihm einen Drittanbieter für Audiokonferenzen zugewiesen haben, wird für diesen Benutzer automatisch Microsoft als Audiokonferenzanbieter festgelegt. In diesem Fall müssen Sie zuerst Microsoft als Audiokonferenzanbieter entfernen, bevor Sie einen Drittanbieter für Audiokonferenzen zuweisen können.
  
3. Suchen Sie unter [Microsoft PinPoint](https://go.microsoft.com/fwlink/?LinkId=797530) einen Drittanbieter für Audiokonferenzen. Nehmen Sie Kontakt zu ihm auf, und informieren Sie sich über die Einrichtung.
    
    Vom Anbieter erhalten Sie: 
    
  - **Einwahlnummern (gebührenpflichtig)** und gebührenfreie Telefonnummern, falls verfügbar
    
  - **Konferenz-IDs**, die für alle Benutzer verwendet werden, die Besprechungen planen. Manche ACPs bezeichnen diese als Konferenz-Passcodes.
    
    > [!NOTE]
    > Wenn Sie das Anfangssetup für einen Drittanbieter-ACP durchgeführt haben und Änderungen vornehmen müssen, klicken Sie unten auf der Seite **Microsoft Bridge** auf **Klicken Sie hier, um einen Drittanbieter für Audiokonferenzen zu konfigurieren**. 
  
    > [!NOTE]
    > Wenn Sie einen Benutzer für Audiokonferenzen aktivieren und ihm einen Drittanbieter für Audiokonferenzen zuweisen, werden die Audionummern und Konferenzkennungen (Passcodes) automatisch zu allen **neuen** Skype for Business Online-Besprechungen hinzugefügt, die er erstellt.
  
## Zuweisen eines Drittanbieters für Audiokonferenzen zu einem Benutzer

1. Wählen Sie im **Skype for Business Admin Center**die Option **Benutzer** aus. Wählen Sie den Benutzer in der Liste aus, und klicken Sie im Aktionsbereich auf **Bearbeiten**.
    
2. Klicken Sie auf der Seite mit den Eigenschaften des Benutzers auf **Audio conferencing** (Audiokonferenz), und geben Sie die folgenden Informationen ein:
    
  - **Anbietername**: Wählen Sie den Drittanbieter in der Liste aus.
    
  - **Gebührenpflichtige Standardnummer**: Diese Angabe ist erforderlich.
    
  - **Gebührenfreie Standardnummer**: Diese Angabe ist nicht erforderlich.
    
  - **Konferenzkennung**: Diese Kennung erhalten Sie von Ihrem Audiokonferenzanbieter.
    
3. Klicken Sie auf **Speichern**.
    
4. Senden Sie jedem Benutzer die PIN, die Sie vom Audiokonferenzanbieter erhalten haben. Die PIN ist möglicherweise zum Einwählen als Organisator oder Gesprächsleiter der Telefonkonferenz erforderlich.
    
    > [!NOTE]
    > Wenn Sie einen Drittanbieter für Audiokonferenzen verwenden, können Sie keine PINs für Besprechungsorganisatoren anzeigen oder festlegen. 
  
## Zuweisen eines Drittanbieters für Audiokonferenzen zu zahlreichen Benutzern gleichzeitig

1. Wählen Sie im **Skype for Business Admin Center**die Optionen **Audio conferencing** (Audiokonferenz) > **Microsoft Bridge** aus. Klicken Sie am Seitenende auf den Link in **Wenn Sie stattdessen einen externen Audiokonferenzanbieter konfigurieren möchten, klicken Sie auf**.
    
    > [!NOTE]
    > Wenn Sie das Anfangssetup für einen Drittanbieter-ACP durchgeführt haben und Änderungen vornehmen müssen, klicken Sie unten auf der Seite **Microsoft Bridge** auf **Klicken Sie hier, um einen Drittanbieter für Audiokonferenzen zu konfigurieren**. 
  
2. Klicken Sie auf der Seite **Konfigurieren eines externen Audiokonferenzanbieters** unter **Benutzer importieren und exportieren** auf **Export-Assistent**. Befolgen Sie dann die Schritte im **Assistenten zum Exportieren von Benutzern**. Wenn Sie fertig sind, haben Sie eine Datei, in der die Benutzer aufgelistet sind, die Sie für Audiokonferenzen einrichten möchten. 
    
3. Senden Sie die erstellte Datei an Ihren Drittanbieter für Audiokonferenzen. Er fügt die Audiokonferenzinformationen für die in der Datei aufgelisteten Personen hinzu und sendet die Datei an Sie zurück.
    
4. Prüfen Sie nach, ob die zurückgesandte Datei die richtigen Informationen enthält. Es sind Fälle vorgekommen, in denen nicht für jede in der Datei aufgelistete Person die richtigen Informationen angegeben waren.
    
5. Klicken Sie auf der Seite **Konfigurieren eines externen Audiokonferenzanbieters** unter **Benutzer importieren und exportieren** auf **Import-Assistent**, und befolgen Sie dann die Schritte im **Assistenten zum Importieren von Benutzern**.
    
6. Senden Sie jedem Benutzer die PIN, die Sie vom Audiokonferenzanbieter erhalten haben. Die PIN ist möglicherweise zum Einwählen als Organisator oder Gesprächsleiter der Telefonkonferenz erforderlich.
    
    > [!NOTE]
    > Wenn Sie einen Drittanbieter für Audiokonferenzen verwenden, können Sie keine PINs für Besprechungsorganisatoren anzeigen oder festlegen. 
  
## Verwendung eines Drittanbieters für Audiokonferenzen

Wenn Sie sich in einem Land/einer Region befinden, in dem/der Audiokonferenzen in Office 365 nicht verfügbar sind, die Servicequalität aufgrund des Standorts schlecht ist oder Sie einen Vertrag mit einem Drittanbieter für Audiokonferenzen abgeschlossen haben, sollten Sie einen Drittanbieter für Audiokonferenzen verwenden. Andernfalls empfehlen wir Microsoft als Audiokonferenzanbieter.
  
## Automatisieren der Zuweisung des externen Audiokonferenzanbieters anhand von Windows PowerShell

- Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Set-CsUserAcp](https://go.microsoft.com/fwlink/?LinkId=716851) nutzen.
    
    > [!NOTE]
    > Um den Audioanbieter von Microsoft in einen Drittanbieter für Audiokonferenzen zu ändern, müssen Sie Microsoft als Audiokonferenzanbieter entfernen. Dazu können Sie das Cmdlet [Disable-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617692 ) verwenden.
  
- Weitere Informationen zur Nutzung von Windows PowerShell finden Sie unter [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038).
    
## Was muss ich sonst noch wissen?

Jeder Benutzer in der Organisation kann nur einen Audiokonferenzanbieter verwenden. Informationen zum Ändern des Audiokonferenzanbieters für einen Benutzer in Microsoft finden Sie unter [Wechseln zu Microsoft als Audiokonferenzanbieter für einen Benutzer](moving-a-user-s-audio-conferencing-provider-to-microsoft.md) oder[Zuweisen von Microsoft als Audiokonferenzanbieter](assign-microsoft-as-the-audio-conferencing-provider.md).
  
## Verwandte Themen

[Einrichten von Audiokonferenzen für Skype for Business und Microsoft Teams](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)
  
[Einrichten von Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  

