---
title: Einrichten von und Problembehandlung bei Skype for Business Online-Delegierung
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: In diesem Artikel wird erläutert, wie Sie die Skype for Business Online-Delegierung einrichten und beheben. Dieser Artikel enthält Anleitungen für Setup Empfehlungen, bewährte Methoden und Schritte zur Problembehandlung.
ms.openlocfilehash: 0528bbb3dc25e085d38f86c040eb5129c9d039c1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285244"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a>Einrichten von und Problembehandlung bei Skype for Business Online-Delegierung

In diesem Artikel wird erläutert, wie Sie die Skype for Business Online-Delegierung einrichten und beheben. Dieser Artikel enthält Anleitungen für Setup Empfehlungen, bewährte Methoden und Schritte zur Problembehandlung.
  
## <a name="guidelines-and-requirements"></a>Richtlinien und Anforderungen

### <a name="guidelines-for-delegation"></a>Richtlinien für die Delegierung

Die Einrichtung und die ordnungsgemäße Funktionsweise der Delegierung hängen davon ab, wie Sie diesen Richtlinien folgen:
  
- Sie müssen den Skype for Business 2015-voll Client mit den neuesten Updates oder dem vollständigen Skype for Business 2016-Client verwenden.
    
- Sie müssen den Outlook 2013-Client mit den neuesten Updates oder dem Outlook 2016-Client verwenden.
    
- Stellen Sie sicher, dass der delegator-und stell Vertretungs Computer über ein Outlook-e-Mail-Profil verfügt, das das primäre oder Standardprofil darstellt. Dieses e-Mail-Profil sollte nur ein Konto enthalten.
    
- Skype for Business für den delegierenden und den Stellvertreter sollten Online-Benutzer sein. Außerdem müssen die Exchange Server-Postfächer für jedes Konto entweder online sein oder beide lokal sein.
    
- Sowohl der delegator als auch der Delegat sollten dieselbe Hauptversion von Outlook verwenden.
    
- Der **EnableExchangeDelegateSync** -Attributwert sollte in der Clientrichtlinie auf " **true** " festgelegt werden. Sie können diese Einstellung überprüfen, indem Sie das Cmdlet " **Get-CSClientPolicy** " im PowerShell-Modul von Skype for Business Online ausführen.
    
- Sowohl der delegator als auch der Delegat müssen bei Skype for Business und Outlook gleichzeitig auf unterschiedlichen Workstations angemeldet sein.
    
- Freigegebene Postfächer werden für die Skype for Business Online-Delegation nicht unterstützt. Dies liegt daran, dass das freigegebene Postfach nicht über die **sendonbehalf** -Zugriffssteuerungsliste (ACL) verfügt.
    
### <a name="skype-for-business-client-version-support"></a>Support für Skype for Business-Client Version

||**Outlook 2013**|**Outlook 2016**|
|:-----|:-----|:-----|
|**Lync/Skype for Business-Basis Client**| Nicht unterstützt |Nicht unterstützt
|**Skype for Business 2015**|Unterstützt | Unterstützt|
|**Skype for Business 2016**|Unterstützt | Unterstützt|

   
### <a name="licensing-requirements"></a>Lizenzierungsanforderungen

**Enterprise E3-Lizenzierungs Szenario**

|**Lizenz**|**Clients**|**Hinweise**|
|:-----|:-----|:-----|
|Enterprise E3  <br/> |Lync 2013 (Skype for Business 2015), verwendet mit Outlook 2013 oder Outlook 2016  <br/> Skype for Business 2016, verwendet mit Outlook 2013 oder Outlook 2016  <br/> |Der Skype for Business Basic-Client unterstützt keine Delegierung.  <br/> Für Mac-Clients können Sie Anrufe, aber nicht Besprechungen delegieren.  <br/> |
|Enterprise E3 mit Office 365 Phone System + Office 365 xCalling-Plan  <br/> |Lync 2013 (Skype for Business 2015), verwendet mit Outlook 2013 oder Outlook 2016  <br/> Skype for Business 2016, verwendet mit Outlook 2013 oder Outlook 2016  <br/> Lync für Mac 2011  <br/> |Der Skype for Business Basic-Client unterstützt keine Delegierung.  <br/> Für Mac-Clients können Sie Anrufe, aber nicht Besprechungen delegieren.  <br/> |
   
**Enterprise E5-Lizenzierungs Szenario**

|**Lizenz**|**Clients**|**Hinweise**|
|:-----|:-----|:-----|
|Enterprise E5  <br/> |Lync 2013 (Skype for Business 2015) wird in Verbindung mit Outlook 2013 oder Outlook 2016 verwendet.  <br/> Skype for Business 2016, verwendet mit Outlook 2013 oder Outlook 2016  <br/> |Der Skype for Business Basic-Client unterstützt keine Delegierung.  <br/> Für Mac-Clients können Sie Anrufe, aber nicht Besprechungen delegieren.  <br/> |
|Enterprise E5 Plus Office 365-Anrufplan  <br/> |Skype for Business für Mac 2016  <br/> Lync 2013 (Skype for Business 2015), verwendet mit Outlook 2013 oder Outlook 2016  <br/> Skype for Business 2016, verwendet mit Outlook 2013 oder Outlook 2016  <br/> Lync für Mac 2011  <br/> |Der Skype for Business Basic-Client unterstützt keine Delegierung.  <br/> Für Mac-Clients können Sie Anrufe, aber nicht Besprechungen delegieren.  <br/> |
   
## <a name="set-up-and-verify-delegation"></a>Einrichten und Überprüfen der Delegierung

Führen Sie die folgenden Schritte aus, um die Skype for Business Online-Delegierung einzurichten:
  
### <a name="for-windows-clients"></a>Für Windows-Clients

 **Registerkarte "Anrufweiterleitung"**
  
1. Wählen Sie **Extras** > **Optionen** > **Anrufweiterleitungseinstellungen**aus.
    
2. Wählen Sie **meine Stell Vertretungs Mitglieder bearbeiten**aus.
    
3. Wählen Sie **Hinzufügen**aus, wählen Sie die Stellvertretung aus, die Sie hinzufügen möchten, und wählen Sie dann **OK**aus.
    
 **Keine Registerkarte "Anrufweiterleitung"**
  
1. Wählen Sie in Outlook **Datei** > **Kontoeinstellungen** > **Stellvertreterzugriff** > **Hinzufügen**aus.
    
2. Suchen Sie den Namen der Person, die die Stellvertretung sein soll, und fügen Sie Sie hinzu.
    
3. Wählen Sie das Menü **Kalender** aus, und wählen Sie dann **Editor (kann Elemente lesen, erstellen und ändern)** aus.
    
### <a name="for-mac-clients---lync"></a>Für Mac-Clients – lync

 **Registerkarte "Anrufweiterleitung"**
  
- Wenn der Client keine Registerkarte " **Anrufweiterleitung** " hat, die über den Link " **meine Stell Vertretungs Mitglieder bearbeiten** " verfügt und sich der delegator auf einem Mac-Computer befindet, muss sich der Delegat bei einem Windows-basierten Computer anmelden, um die Delegierung einzurichten. Dies liegt daran, dass Mac-Clients keine MAPI-Verbindungen herstellen können und dies eine Voraussetzung für die Einrichtung von Skype for Business-Delegierung aus Outlook ist.
    
### <a name="verify-success"></a>Überprüfen des Erfolgs

Wenn die Einrichtung erfolgreich ist, sollte die Stellvertretung sehen, dass **Sie als Stellvertretung für < Name>-Nachricht hinzugefügt wurden** , und dass die **Personen, für die ich Anrufe** verwalte, für die Gruppe erstellt werden. Der Delegat sollte sehen, dass die Gruppe **Stellvertretungen** erstellt wird.
  
> [!NOTE]
> Delegierungsberechtigungen werden in der Regel innerhalb von 30 Minuten nach dem Setupvorgang angezeigt. Dieser Vorgang kann jedoch bis zu 24 Stunden dauern. 
  
## <a name="troubleshooting"></a>Problembehandlung

### <a name="common-issues"></a>Häufig auftretende Probleme

- > **Ausgabe 1** Der Delegat-Eintrag wird weiterhin in den Personen angezeigt, die **ich für die Gruppe Anrufe verwalten** , nachdem der Delegat den Delegaten aus dem Outlook-Client entfernt hat.
    
  - > **Auflösung 1** Klicken Sie im Skype for Business-Client mit der rechten Maustaste auf den Stellvertreter in der Gruppe **Stellvertretungen** , und wählen Sie dann **aus Gruppe entfernen aus**.
    
- > **Problem 2** Nachdem der Zugriff auf die Stellvertretung über den Outlook-Client gewährt wurde, werden weder die Bestätigungsnachricht noch die Personen, die **ich für** die Gruppe verwaltet, für die Stellvertretung angezeigt.
    
  - > **Auflösung 2** Entfernen Sie die Delegierung aus dem Outlook-Client, warten Sie etwa 15 Minuten für die Replikation, und fügen Sie dann die Stellvertretung erneut hinzu.
    
### <a name="other-common-issues"></a>Andere häufige Probleme

- Die Delegierung funktioniert nicht, wenn der Schwellenwert von 25 Delegaten und 25 Stellvertretungen überschritten wird.
    
- Der Skype for Business Basic-Client wird nicht unterstützt.
    
    > [!NOTE]
    > Wenn Sie den Skype for Business Basic-Client installieren, wird die Delegierung entfernt und unterbrochen. 
  
- Wenn der **MAPI-Status** Wert nicht in **Ordnung**ist, stellen Sie sicher, dass die **SIP** -und **SMTP-** Werte übereinstimmen.
    
    > [!NOTE]
    > Es kann einige Minuten dauern, bis der MAPI-Status nach dem ersten Start von Skype for Business und Outlook als **"OK"** angezeigt wird.
  
- Das Erstellen einer Sicherheitsgruppe und das Hinzufügen von Delegierungsberechtigungen für diese Sicherheitsgruppe werden nicht unterstützt.
    
- MAPI steht nicht zur Verfügung. Lesen Sie [den Fehler "MAPI-nicht verfügbar" in Skype for Business 2016-Client](https://support.microsoft.com/en-us/help/3147130).
    
- Auf das Exchange Online-Postfach kann über den Skype for Business-Client nicht zugegriffen werden. Wenn dies der Fall ist, führen Sie den [Outlook-Verbindungstest](https://testconnectivity.microsoft.com/) aus, um sicherzustellen, dass er verläuft.
    
## <a name="related-topics"></a>Verwandte Themen
[Einrichten von Skype for Business Online](set-up-skype-for-business-online.md)

[Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen](let-skype-for-business-users-add-skype-contacts.md)

  
 
