---
title: "Richten Sie ein und Problembehandlung bei Skype für Business Online Delegierung"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: "In diesem Artikel wird erläutert, wie eingerichtet und Problembehandlung bei Skype für Business Online Delegierung. Dieser Artikel enthält eine Anleitung für Setup Empfehlungen, bewährte Methoden und Schritte zur Problembehandlung."
ms.openlocfilehash: bf3bf61a633366408e2584a89dfee9ad771ce78e
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2017
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a>Richten Sie ein und Problembehandlung bei Skype für Business Online Delegierung

In diesem Artikel wird erläutert, wie eingerichtet und Problembehandlung bei Skype für Business Online Delegierung. Dieser Artikel enthält eine Anleitung für Setup Empfehlungen, bewährte Methoden und Schritte zur Problembehandlung.
  
## <a name="guidelines-and-requirements"></a>Richtlinien und Anforderungen

### <a name="guidelines-for-delegation"></a>Richtlinien für die Delegierung

Einrichten und erste Delegierung ordnungsgemäß funktioniert, hängt Sie die folgenden Richtlinien:
  
- Sie müssen die Skype für vollständige Business 2015-Client mit den neuesten Updates oder die Skype für Business 2016 vollständige Client verwenden werden.
    
- Sie müssen die Outlook 2013-Clients mit den neuesten Updates oder Outlook 2016 Clients verwenden.
    
- Stellen Sie sicher, dass die Delegator und stellvertretercomputern einem Outlook-Mail-Profil, das die primäre ist oder das Standardprofil verwendet werden. Diese e-Mail-Profil sollte nur ein Konto enthalten.
    
- Skype für Unternehmen für Stellvertreters und den Delegaten sollte Online-Benutzer sein. Darüber hinaus die Exchange Server Postfächer für jedes Konto müssen entweder beide Online oder beide lokalen sein.
    
- Sowohl die Delegator auch der Stellvertreter sollten die gleiche Hauptversion von Outlook verwenden.
    
- Der Attributwert **EnableExchangeDelegateSync** sollte auf **true fest,** in die Clientrichtlinie festgelegt werden. Sie können diese Einstellung überprüfen, indem Sie das Cmdlet **Get-CSClientPolicy** in der Skype für Business Online-PowerShell-Modul ausgeführt.
    
- Sowohl die Delegator auch der Stellvertreter müssen Skype für Unternehmen und Outlook gleichzeitig auf verschiedenen Arbeitsstationen anmelden, um.
    
- Freigegebene Postfächer werden für die Business Online Delegierung für Skype nicht unterstützt. Dies ist, da das freigegebene Postfach die Zugriffssteuerungsliste (ACL) für das **sendonbehalf werden standardmäßig** keine.
    
### <a name="skype-for-business-client-version-support"></a>Skype für Business Version Clientunterstützung

||**Outlook 2013**|**Outlook 2016**|
|:-----|:-----|:-----|
|**Lync/Skype für grundlegende Business-Client**| Nicht unterstützt |Nicht unterstützt
|**Skype für Business 2015**|Unterstützt | Unterstützt |
|**Skype für Business 2016**|Unterstützt | Unterstützt |

   
### <a name="licensing-requirements"></a>Lizenzanforderungen

**Lizenzierung Enterprise E3-Szenario**

|**Lizenz**|**Clients**|**Notizen**|
|:-----|:-----|:-----|
|Enterprise E3  <br/> |Lync 2013 (Skype für Business 2015) mit Outlook 2013 oder Outlook 2016 verwendet  <br/> Skype für Outlook 2013 oder Outlook 2016 verwendete Business 2016  <br/> |Skype für Business Basic-Client unterstützt keine Delegierung.  <br/> Für Macintosh-Clients können Sie Anrufe jedoch nicht in Besprechungen delegieren.  <br/> |
|Enterprise-E3 mit Office 365-Telefonsystem + Office 365 xCalling Plan  <br/> |Lync 2013 (Skype für Business 2015) mit Outlook 2013 oder Outlook 2016 verwendet  <br/> Skype für Outlook 2013 oder Outlook 2016 verwendete Business 2016  <br/> Lync für Mac 2011  <br/> |Skype für Business Basic-Client unterstützt keine Delegierung.  <br/> Für Macintosh-Clients können Sie Anrufe jedoch nicht in Besprechungen delegieren.  <br/> |
   
**Lizenzierung E5 Enterprise-Szenario**

|**Lizenz**|**Clients**|**Notizen**|
|:-----|:-----|:-----|
|Enterprise-E5  <br/> |Lync 2013 (Skype für Business 2015) mit Outlook 2013 oder Outlook 2016.  <br/> Skype für Outlook 2013 oder Outlook 2016 verwendete Business 2016  <br/> |Skype für Business Basic-Client unterstützt keine Delegierung.  <br/> Für Macintosh-Clients können Sie Anrufe jedoch nicht in Besprechungen delegieren.  <br/> |
|Enterprise-E5 plus Office 365 aufrufen Plan  <br/> |Skype für Unternehmen für Mac 2016  <br/> Lync 2013 (Skype für Business 2015) mit Outlook 2013 oder Outlook 2016 verwendet  <br/> Skype für Outlook 2013 oder Outlook 2016 verwendete Business 2016  <br/> Lync für Mac 2011  <br/> |Skype für Business Basic-Client unterstützt keine Delegierung.  <br/> Für Macintosh-Clients können Sie Anrufe jedoch nicht in Besprechungen delegieren.  <br/> |
   
## <a name="set-up-and-verify-delegation"></a>Einrichten und Überprüfen der Delegierung

Um Skype für Business Online Delegierung einzurichten, gehen Sie folgendermaßen vor:
  
### <a name="for-windows-clients"></a>Für Windows-clients

 **Registerkarte für die anrufweiterleitung**
  
1. Wählen Sie **Extras** > **Optionen** > **Einstellungen der Anrufweiterleitung**.
    
2. Wählen Sie **Stellvertretungen bearbeiten**.
    
3. Wählen Sie **Hinzufügen**, wählen Sie die Stellvertretung, die Sie hinzufügen möchten, und wählen Sie dann auf **OK**.
    
 **Keine Registerkarte Anrufweiterleitung**
  
1. Wählen Sie in Outlook die **Datei** > **Kontoeinstellungen** > **Stellvertretungszugriff** > **Hinzufügen**.
    
2. Suchen Sie nach, und fügen Sie den Namen der Person ein, die die Stellvertretung sein soll.
    
3. Wählen Sie im Menü **Kalender** aus, und wählen Sie **Editor (können lesen, erstellen und Ändern von Elementen)**.
    
### <a name="for-mac-clients---lync"></a>Für Macintosh-Clients – Lync

 **Registerkarte für die anrufweiterleitung**
  
- Wenn der Client verfügt nicht über eine Registerkarte für die **Anrufweiterleitung** , die über den Link **Stellvertretungen bearbeiten** und Stellvertreters sich auf einem Mac befindet, muss Stellvertreters auf einem Windows-basierten Computer anmelden, um die Delegierung einrichten. Dies ist, da Macintosh-Clients können keine MAPI-Verbindungen stellen, und dies ist eine Voraussetzung für die Business-Delegierung aus Outlook Skype herstellen.
    
### <a name="verify-success"></a>Überprüfen des Erfolgs des Updates

Wenn die Installation erfolgreich ist, die Stellvertretung sollte angezeigt werden die **Sie als Stellvertreter für < Name > hinzugefügt wurden** Meldung und außerdem, die die **Personen, für die ich Anrufe verwalte** -Gruppe wird erstellt. Stellvertreters sollte angezeigt werden, dass die Gruppe **Stellvertretungen** erstellt wird.
  
> [!NOTE]
> Delegierungsberechtigungen werden in der Regel innerhalb von 30 Minuten der Installation angezeigt. Dieser Vorgang kann jedoch bis zu 24 Stunden dauern. 
  
## <a name="troubleshooting"></a>Problembehandlung

### <a name="common-issues"></a>Häufige Probleme

- > **Problem 1** Der Eintrag Delegat wird weiterhin in der Gruppe **Personen, für die ich Anrufe verwalte** angezeigt, nachdem Stellvertreters des Delegaten aus der Outlook-Client entfernt wurde.
    
  - > **Lösung 1** Auf der Skype für Business-Client mit der rechten Maustaste der stellvertretungs in der Gruppe **Stellvertretungen** , und wählen Sie dann auf **aus Gruppe entfernen**.
    
- > **Problem 2** Nachdem Delegieren des Zugriffs über den Outlook-Client gewährt wurde, werden für die Stellvertretung die Meldung zur Bestätigung weder der **Personen, für die ich Anrufe verwalte** Gruppe angezeigt.
    
  - > **Lösung 2** Entfernen Sie die Stellvertretung aus der Outlook-Client, warten Sie 15 Minuten für die Replikation, und fügen Sie die Stellvertretung erneut.
    
### <a name="other-common-issues"></a>Andere allgemeine Probleme

- Delegierung funktioniert nicht, wenn der Schwellenwert von 25 Delegators und 25 Delegaten überschritten wird.
    
- Die Skype für Business Basic-Client wird nicht unterstützt.
    
    > [!NOTE]
    > Wenn Sie die Skype für Business Basic-Client installieren, entfernt und Delegierung aufgehoben. 
  
- Wenn der Wert des **MAPI-Status** nicht **OK**ist, stellen Sie sicher, dass die **SIP-** und **SMTP** -Werten entsprechen.
    
    > [!NOTE]
    > Es kann mehrere Minuten dauern für den MAPI-Status als **OK** angezeigt, nach dem ersten Skype für Unternehmen und Outlook Start.
  
- Erstellen einer Sicherheitsgruppe und Hinzufügen von Delegierungsberechtigungen für diese Sicherheitsgruppe wird nicht unterstützt.
    
- MAPI ist nicht verfügbar. [Fehler in Skype für Business 2016 Client "MAPI nicht verfügbar"](https://support.microsoft.com/en-us/help/3147130)angezeigt.
    
- Exchange Online-Postfach ist nicht verfügbar, über die Skype für Business-Client. Wenn dies der Fall ist, führen Sie den [Outlook-Verbindungstest](https://testconnectivity.microsoft.com/) dafür sorgen, dass er übergibt.
    
## <a name="related-topics"></a>Verwandte Themen
[Einrichten von Skype for Business Online](set-up-skype-for-business-online.md)

[Können Sie Skype für Unternehmensbenutzer Skype-Kontakte hinzufügen](let-skype-for-business-users-add-skype-contacts.md)
