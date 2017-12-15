---
title: "Einrichten von Voicemail für Telefonsysteme - Administratorhilfe"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/15/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
description: "Learn how to set up the phone system (Cloud PBX) voicemail for your Skype for Business users. "
---

# Einrichten von Voicemail für Telefonsysteme - Administratorhilfe

Dieser Artikel richtet sich an [Informationen zu Administratorrollen von Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), die die Voicemailfunktion für Telefonsysteme für alle Mitarbeiter im Unternehmen einrichten möchten.
  
> [!NOTE]
> Voicemail für Telefonsysteme unterstützt die Ablage von Voicemailnachrichten nur in Exchange-Postfächern. E-Mail-Systeme von Drittanbietern werden nicht unterstützt. Als Ausweichmechanismus kann Voicemail für Telefonsysteme Nachrichten über SMTP erneut senden. Das bedeutet, dass Benutzer mit einem Postfach in einem E-Mail-System eines Drittanbieters ihre Voicemailnachrichten ohne garantierte Dienstbetriebszeit oder andere Voicemailfunktionen (beispielsweise Ändern ihrer Begrüßung und anderer Einstellungen) erhalten. 
  
## Reine Cloudumgebungen: Einrichten von Voicemail für Telefonsysteme

Für Benutzer von Skype for Business Online und Anrufplänen wird Voicemail für Telefonsysteme automatisch eingerichtet und für Benutzer bereitgestellt, nachdem Sie den Benutzern eine **Telefonsystemlizenz** und eine Telefonnummer zugewiesen haben.
  
1. Wenn die Telefonsystemfunktion nicht in Ihrem Plan enthalten ist, müssen Sie möglicherweise Lizenzen für das **Telefonsystem**-Add-On kaufen. Sie müssen möglicherweise auch eine Exchange Online-Lizenz kaufen. Weitere Informationen finden Sie unter [Add-On-Lizenzierung für Skype for Business und Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
2. [Zuweisen oder Entfernen von Lizenzen für Office 365 Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), die [Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) und die Exchange Online-Lizenzen den jeweiligen Personen in Ihrem Unternehmen zu. Anschließend können sie Voicemailnachrichten empfangen.
    
3. Seit März 2017 ist die Unterstützung für Voicemailtranskription standardmäßig für alle Organisationen und Benutzer aktiviert. Sie können die Transkription für Ihre Organisation mithilfe von Windows PowerShell deaktivieren, indem Sie die folgenden Schritte ausführen.
    
## Telefonsystem in lokalen Umgebungen

Den folgenden Informationen können Sie entnehmen, wie Sie Voicemail für Telefonsysteme für die Verwendung in lokalen Umgebungen mit Anrufplänen konfigurieren.
  
1. Wenn die Telefonsystemfunktion nicht in Ihrem Plan enthalten ist, müssen Sie möglicherweise Lizenzen für das **Telefonsystem**-Add-On kaufen. Sie müssen auch eine Exchange Online-Lizenz kaufen. Weitere Informationen finden Sie unter [Add-On-Lizenzierung für Skype for Business und Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
2. [Zuweisen oder Entfernen von Lizenzen für Office 365 Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), die [Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) und die Exchange Online-Lizenzen den jeweiligen Personen in Ihrem Unternehmen zu.
    
3. Folgen Sie den Anweisungen im Abschnitt **Aktivieren von Benutzern für Telefonsystem-VoIP und Voicemail** des[Konfigurationshandbuchs für die Skype for Business Cloud Connector-Edition](https://technet.microsoft.com/en-us/library/mt605228.aspx).
    
4. Seit März 2017 ist die Unterstützung für Voicemailtranskription standardmäßig für alle Organisationen und Benutzer aktiviert. Sie können die Transkription für Ihre Organisation mithilfe von Windows PowerShell deaktivieren, indem Sie die folgenden Schritte ausführen. 
    
5. Unter [Unterstützung für Azure-PBX-Voicemail für Exchange Server](https://support.microsoft.com/en-us/kb/3195158) können Sie nachlesen, wie Sie die Übermittlung von Azure-Voicemailnachrichten für Telefonsystembenutzer mit lokalen Postfächern konfigurieren.
    
## Einrichten von Voicemailrichtlinien in Ihrer Organisation

Voicemailtranskription ist standardmäßig für alle Organisationen und Benutzer aktiviert. Sie können diese Funktion jedoch mit den Cmdlets [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) und[Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx) steuern.
  
> [!IMPORTANT]
> Sie können mit dem Cmdlet **New-CsOnlineVoiceMailPolicy** keine neue Richtlinieninstanz für Transkription erstellen, und Sie können mit dem Cmdlet **Remove-CsOnlineVoiceMailPolicy** keine vorhandene Richtlinieninstanz entfernen.
  
Sie können die Transkriptionseinstellungen für Ihre Benutzer mit Voicemailrichtlinien verwalten. Um alle verfügbaren Instanzen der Voicemailrichtlinien anzuzeigen, können Sie das Cmdlet [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/en-us/library/mt798311.aspx)[]() verwenden.
  
 **PS C:\\> Get-CsOnlineVoicemailPolicy**
  
![Get-CsOnlineVoiceMailPolicy results window.](../../images/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### Deaktivieren der Aufzeichnung für Ihre Organisation

Die Transkription ist standardmäßig für Ihre Organisation aktiviert. Sie können sie aber mit dem Cmdlet [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) deaktivieren. Führen Sie dazu Folgendes aus:
  
```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### Aufzeichnung für einen Benutzer deaktivieren

Benutzerrichtlinien werden vor den Standardeinstellungen für die Organisation ausgewertet. Wenn Voicemailtranskription beispielsweise für alle Benutzer aktiviert ist, können Sie mit dem Cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx) eine Richtlinie zuweisen, um die Transkription für einen bestimmten Benutzer zu deaktivieren.
  
Führen Sie zum Deaktivieren eines einzelnen Benutzers den folgenden Dienst aus:
  
```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> Der Voicemaildienst in Office 365 cacht Voicemailrichtlinien und aktualisiert den Cache alle 4 Stunden. Es kann also bis zu 4 Stunden dauern, bis die von Ihnen vorgenommenen Richtlinienänderungen angewendet werden. 
  
## Unterstützen Sie Ihre Benutzer bei der Verwendung der Skype for Business-Voicemail-Funktionen.

Wir bieten Schulungsinformationen und Artikel an, damit Ihre Benutzer erfolgreich mit Skype for Business-Voicemail arbeiten können. Machen Sie Ihre Benutzer auf folgende Artikel aufmerksam:
  
- [Prüfen von Skype for Business-Voicemail und -Optionen](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): In diesem Artikel wird erläutert, wie Sie Ihre Voicemail in Skype for Business abhören, Ihre Voicemailansage ändern und sich Ihre Voicemail in unterschiedlichen Geschwindigkeiten anhören.
    
- [Skype for Business 2016-Schulung](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)
    
## Verwandte Themen

[Einrichten von Skype for Business Online](../../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[Hier ist das Ergebnis mit Telefonsystem in Office 365](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system-in-office-365.md)
  

