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
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: In diesem Artikel wird erläutert, wie Sie eine Onlinedelegierung Skype for Business und eine Problembehandlung dafür finden. Dieser Artikel enthält Anleitungen zu Einrichtungsempfehlungen, bewährten Methoden und Schritten zur Problembehandlung.
ms.openlocfilehash: e5c710849f5829a4a270dc327f71d98185e85c89
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239824"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a>Einrichten von und Problembehandlung bei Skype for Business Online-Delegierung

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

In diesem Artikel wird erläutert, wie Sie eine Onlinedelegierung Skype for Business und eine Problembehandlung dafür finden. Dieser Artikel enthält Anleitungen zu Einrichtungsempfehlungen, bewährten Methoden und Schritten zur Problembehandlung.
  
## <a name="guidelines-and-requirements"></a>Richtlinien und Anforderungen

### <a name="guidelines-for-delegation"></a>Richtlinien für Delegierung

Das Einrichten und Erhalten einer ordnungsgemäßen Stellvertretung hängt davon ab, dass Sie die folgenden Richtlinien befolgen:
  
- Sie müssen den vollständigen Skype for Business 2015-Client mit den neuesten Updates oder den vollständigen Skype for Business 2016-Client verwenden.
    
- Sie müssen den Outlook 2013-Client mit den neuesten Updates oder den Client Outlook 2016 verwenden.
    
- Stellen Sie sicher, dass die Delegator- und Stellvertretungscomputer über ein Outlook-Mail-Profil verfügen, das das primäre oder das Standardprofil ist. Dieses E-Mail-Profil sollte nur ein Konto enthalten.
    
- Skype for Business delegieren und die Stellvertretung sollte Onlinebenutzer sein. Darüber hinaus müssen Exchange Server Postfächer für jedes Konto entweder online oder beide lokal sein.
    
- Sowohl der Delegator als auch der Delegat sollten dieselbe Hauptversion des Outlook.
    
- Der **EnableExchangeDelegateSync-Attributwert** sollte in der Clientrichtlinie auf **true** festgelegt werden. Sie können diese Einstellung überprüfen, indem Sie das **Get-CSClientPolicy-Cmdlet** im Skype for Business Online PowerShell-Modul ausführen.
    
- Sowohl der Delegator als auch der Delegat müssen auf verschiedenen Arbeitsstationen Skype for Business und Outlook gleichzeitig angemeldet sein.
    
- Freigegebene Postfächer werden für die Onlinedelegierung Skype for Business unterstützt. Der Grund dafür ist, dass das freigegebene Postfach nicht über die **sendonbehalf-Zugriffssteuerungsliste** (Access Control List, ACL) verfügen.
    
### <a name="skype-for-business-client-version-support"></a>Skype for Business der Clientversionsunterstützung

||**Outlook 2013**|**Outlook 2016**|
|:-----|:-----|:-----|
|**Lync/Skype for Business Basic Client**| Nicht unterstützt |Nicht unterstützt
|**Skype for Business 2015**|Unterstützt | Unterstützt|
|**Skype for Business 2016**|Unterstützt | Unterstützt|

   
### <a name="licensing-requirements"></a>Lizenzierungsanforderungen

**Enterprise E3-Lizenzierungsszenario**

|**Lizenz**|**Clients**|**Hinweise**|
|:-----|:-----|:-----|
|Enterprise E3  <br/> |Lync 2013 (Skype for Business 2015) in Outlook 2013 oder Outlook 2016  <br/> Skype for Business 2016 in Outlook 2013 oder Outlook 2016  <br/> |Skype for Business Der einfache Client unterstützt keine Delegierung.  <br/> Bei Mac-Clients können Sie Anrufe delegieren, aber keine Besprechungen.  <br/> |
|Enterprise E3 mit Office 365-Telefonsystem + Office 365 xCalling Plan  <br/> |Lync 2013 (Skype for Business 2015) in Outlook 2013 oder Outlook 2016  <br/> Skype for Business 2016 in Outlook 2013 oder Outlook 2016  <br/> Lync für Mac 2011  <br/> |Skype for Business Der einfache Client unterstützt keine Delegierung.  <br/> Bei Mac-Clients können Sie Anrufe delegieren, aber keine Besprechungen.  <br/> |
   
**Enterprise E5-Lizenzierungsszenario**

|**Lizenz**|**Clients**|**Hinweise**|
|:-----|:-----|:-----|
|Enterprise E5  <br/> |Lync 2013 (Skype for Business 2015) in Outlook 2013 oder Outlook 2016.  <br/> Skype for Business 2016 in Outlook 2013 oder Outlook 2016  <br/> |Skype for Business Der einfache Client unterstützt keine Delegierung.  <br/> Bei Mac-Clients können Sie Anrufe delegieren, aber keine Besprechungen.  <br/> |
|Enterprise E5 plus Office 365 Anrufplan  <br/> |Skype for Business für Mac 2016  <br/> Lync 2013 (Skype for Business 2015) in Outlook 2013 oder Outlook 2016  <br/> Skype for Business 2016 in Outlook 2013 oder Outlook 2016  <br/> Lync für Mac 2011  <br/> |Skype for Business Der einfache Client unterstützt keine Delegierung.  <br/> Bei Mac-Clients können Sie Anrufe delegieren, aber keine Besprechungen.  <br/> |
   
## <a name="set-up-and-verify-delegation"></a>Einrichten und Überprüfen der Delegierung

Führen Sie zum Einrichten Skype for Business Onlinedelegierung die folgenden Schritte aus:
  
### <a name="for-windows-clients"></a>Für Windows Clients

 **Registerkarte "Anruf weiterleitung"**
  
1. Wählen **Sie**  >  **Extras Optionen**  >  **Anrufanruf Einstellungen** aus.
    
2. Wählen **Sie Stellvertretungsmitglieder bearbeiten aus.**
    
3. Wählen **Sie Hinzufügen** aus, wählen Sie die Stellvertretung aus, die Sie hinzufügen möchten, und wählen Sie dann OK **aus.**
    
 **Keine Registerkarte "Anruf weiterleitung"**
  
1. Wählen Outlook Dateikonto   >  **aus, und Einstellungen**  >  **Zugriffsrechte für Stellvertretung**  >  **hinzufügen** aus.
    
2. Suchen Sie den Namen der Person, die die Stellvertretung werden soll, und fügen Sie ihn hinzu.
    
3. Wählen Sie **das Menü** Kalender und dann **Editor (Elemente lesen, erstellen und ändern) aus.**
    
### <a name="for-mac-clients---lync"></a>Für Mac-Clients – Lync

 **Registerkarte "Anruf weiterleitung"**
  
- Wenn der Client keine  Registerkarte Anruf weiterleitung mit  dem Link Stellvertretungsmitglieder bearbeiten hat und sich die Delegierung auf einem Mac-Computer befindet, muss sich die Delegator bei einem Windows-basierten Computer anmelden, um die Stellvertretung einrichten zu können. Dies liegt daran, dass Mac-Clients keine MAPI-Verbindungen herstellen können, und dies ist eine Anforderung zum Einrichten Skype for Business Delegierung Outlook.
    
### <a name="verify-success"></a>Überprüfen des Erfolgs

Wenn die Einrichtung erfolgreich war, sollte der Stellvertretung die Nachricht Sie wurden als Stellvertretung  für < Name **>** hinzugefügt und außerdem angezeigt werden, dass die Gruppe Personen, für die ich Anrufe verwalte erstellt wurde. Der Delegator sollte sehen, dass die Gruppe **Stellvertretung** erstellt wurde.
  
> [!NOTE]
> Delegierungsberechtigungen werden in der Regel innerhalb von 30 Minuten nach dem Setup angezeigt. Dieser Vorgang kann jedoch bis zu 24 Stunden dauern. 
  
## <a name="troubleshooting"></a>Problembehandlung

### <a name="common-issues"></a>Häufige Probleme

- > **Problem 1** Der Stellvertretungseintrag  wird weiterhin in der Gruppe Personen, für die ich Anrufe verwalte angezeigt, nachdem die Stellvertretung die Stellvertretung aus dem Client Outlook entfernt hat.
    
  - > **Auflösung 1** Klicken Sie Skype for Business-Client in der Gruppe Stellvertretung mit der rechten Maustaste auf die Stellvertretung, und wählen Sie **dann Aus Gruppe entfernen aus.** 
    
- > **Problem 2** Nachdem der Zugriff auf die Stellvertretung über den Outlook-Client gewährt wurde, werden weder die Bestätigungsmeldung noch die Gruppe Personen, für die ich Anrufe verwalte für für die Stellvertretung angezeigt. 
    
  - > **Auflösung 2** Entfernen Sie die Delegierung aus Outlook Client, warten Sie etwa 15 Minuten auf Replikation, und fügen Sie dann die Stellvertretung erneut hinzu.
    
### <a name="other-common-issues"></a>Weitere häufige Probleme

- Delegierung funktioniert nicht, wenn der Schwellenwert von 25 Delegierern und 25 Stellvertretung überschritten wird.
    
- Der Skype for Business Basic-Client wird nicht unterstützt.
    
    > [!NOTE]
    > Wenn Sie den Skype for Business Basic-Client installieren, wird die Delegierung entfernt und die Delegierung unterbricht. 
  
- Wenn der **MAPI-Statuswert** nicht **OK** ist, stellen Sie sicher, dass die **SIP-** und **SMTP-Werte** übereinstimmen.
    
    > [!NOTE]
    > Es kann einige Minuten dauern, bis der MAPI-Status als **OK** angezeigt wird, nachdem Sie die Skype for Business und Outlook.
  
- Das Erstellen einer Sicherheitsgruppe und Das Hinzufügen von Delegierungsberechtigungen für diese Sicherheitsgruppe wird nicht unterstützt.
    
- MAPI ist nicht verfügbar. Siehe [Fehler "MAPI nicht verfügbar" im Skype for Business 2016-Client.](https://support.microsoft.com/help/3147130)
    
- Auf Exchange Online Postfach kann nicht über den Client Skype for Business zugegriffen werden. Führen Sie in diesem Fall den [Test Outlook Verbindung aus,](https://testconnectivity.microsoft.com/) um sicherzustellen, dass die Verbindung bestanden wird.
    
## <a name="related-topics"></a>Verwandte Themen
[Einrichten von Skype for Business Online](set-up-skype-for-business-online.md)

[Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen](let-skype-for-business-users-add-skype-contacts.md)

  
 
