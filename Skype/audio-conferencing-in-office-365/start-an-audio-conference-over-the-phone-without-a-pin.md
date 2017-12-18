---
title: "Starten einer Audiokonferenz per Telefon ohne PIN"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/16/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
description: "Learn how to enable or disable anonymous callers from joining a meeting from the Skype for Business admin center or using a PowerShell script. "
---

# Starten einer Audiokonferenz per Telefon ohne PIN

> [!IMPORTANT]
> Dieser Artikel wurde maschinell übersetzt. Bitte beachten Sie den Haftungsausschluss.  
  
Es möglicherweise für Benutzer frustrierend sein, die sich einwählen, um eine Besprechung an, in die Musik hören, da die Skype für Business- oder Microsoft Teams Organisator die Besprechung noch nicht gestartet Besprechungslobby stattfinden soll.
  
Wenn sich der Organisator einer Besprechung in seine Besprechung einwählt, benötigt er zum Starten der Besprechung standardmäßig eine PIN. Sie können dies so einrichten, dass sich jeder in die Besprechung einwählen kann, ohne zur Eingabe einer PIN zum Starten der Besprechung aufgefordert zu werden. Sie können sie so einrichten, dass ein einzelner Benutzer oder alle Benutzer mit eingehenden Verbindungen in Ihrem Unternehmen ihre Besprechungen ohne PIN starten können. Sie können diese Einstellung für einen einzelnen Benutzer im Skype for Business Admin Center aktivieren oder deaktivieren.
  
Eine PIN ist nicht erforderlich, damit der Besprechungsorganisator, wenn jemand die Besprechung aus einem Skype for Business- oder Microsoft Teams-app gestartet hat. Eine PIN ist nur erforderlich, wenn Sie eine Besprechung Organisieren ihrer Besprechung über ein Telefon verknüpft. Die PIN für Besprechungen ist für den Benutzer einwählen gesendet, wenn sie die Lizenz **Audiokonferenzanbieter** zugewiesen sind und für Audiokonferenzanbieter aktiviert sind. Finden Sie unter[Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-audio-conferencing-information.md) und[E-Mails, die automatisch an Benutzer gesendet werden, wenn sich ihre Einwahlkonferenzeinstellungen ändern](emails-that-are-automatically-sent-to-users-when-their-audio-conferencing-settin.md).
  
## Aktivieren oder Deaktivieren anonymer Anrufer für die Teilnahme an einer Besprechung

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.
    
3. Wechseln Sie in der **Skype for Business Admin Center**, im linken Navigationsbereich auf **Audio Konferenzen** > **Benutzer mit eingehenden Verbindungen**.
    
4. Wählen Sie den Benutzer aus der Liste aus und klicken Sie im Bereich „Aktion" auf **Bearbeiten**.
    
5. Aktivieren oder deaktivieren Sie auf der Seite „Eigenschaften" unter **Besprechungsoptionen** die Option **Zulassen, dass nicht authentifizierte Benutzer als erste Teilnehmer an einer Besprechung teilnehmen Wenn nicht, warten sie im Wartebereich, bis ein authentifizierter Benutzer an der Besprechung teilnimmt**.
    
6. Klicken Sie auf **Speichern**.
    
 **So aktivieren oder Deaktivieren von anonymen Anrufern alle des Benutzers Besprechungen mithilfe von Windows Powershell**
  
- Führen Sie Folgendes aus: 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## Was sollten Sie noch wissen?

- Wenn Sie die PIN zurücksetzen möchten, finden Sie unter [Zurücksetzen der Einwahlkonferenz-PIN für einen Benutzer](reset-the-audio-conferencing-pin-for-a-user.md).
    
- Wenn der anonyme Zugriff oder das Starten einer Besprechung ohne PIN aktiviert ist:
    
  - Wenn die Besprechung noch nicht gestartet (es ist keine in der Besprechung noch): ein Anrufer aufgefordert werden, ist er der Organisator, wenn sagt er auf Ja, er nach He Eingaben die PIN für seine PIN aufgefordert werden werden, die Besprechung gestartet wird und der Benutzer wird an der Besprechung teilnehmen.
    
  - Wenn die Besprechung bereits gestartet (Person ist bereits in der Besprechung): ein Anrufer nicht aufgefordert werden, ist er des Organisators und er werden nie für die PIN aufgefordert werden, die Besprechung bereits gestartet wird, wird der Anrufer verknüpfen Sie ihn.
    
- Wenn anonymer Zugriff oder eine PIN zum Starten einer Besprechung keine Anmeldung deaktiviert ist:
    
  - Wenn die Besprechung noch nicht gestartet (es ist keine in der Besprechung noch): ein Anrufer nicht aufgefordert werden, wenn er des Organisators ist, und er nie für die PIN aufgefordert werden werden. Da die Einstellung für des Organisators deaktiviert festgelegt ist, wird die Besprechung starten und anonymen Anrufern werden an der Besprechung teilnehmen.
    
  - Wenn die Besprechung bereits gestartet (Person ist bereits in der Besprechung): ein Anrufer nicht aufgefordert werden, ist er des Organisators und er werden nie für die PIN aufgefordert werden, die Besprechung bereits gestartet wird, wird der Anrufer verknüpfen Sie ihn.
    
## Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Wenn Sie Zeit sparen, oder dies für mehrere Benutzer automatisieren, können Sie das Cmdlet " [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) " verwenden.
    
- In Bezug auf Windows PowerShell dreht sich bei Skype for Business Online alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Sechs Gründe für die Verwendung von Windows PowerShell zur Verwaltung von Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell bietet gegenüber einer alleinigen Verwendung von Office 365 Admin Center in Bezug auf Geschwindigkeit, Einfachheit und Produktivität unzählige Vorteile, z. B. wenn Sie die Einstellungen für viele Benutzer gleichzeitig ändern. In den folgenden Themen erfahren Sie mehr über diese Vorteile:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Haftungsausschluss für maschinelle Übersetzungen**: Dieser Artikel wurde mithilfe eines Computersystems und ohne jegliche Bearbeitung durch Personen übersetzt. Microsoft bietet solche maschinellen Übersetzungen als Hilfestellung für Benutzer ohne Englischkenntnisse an, damit Sie von den Informationen zu Produkten, Diensten und Technologien von Microsoft profitieren können. Da es sich bei diesem Artikel um eine maschinelle Übersetzung handelt, enthält er möglicherweise Fehler in Bezug auf (Fach-)Terminologie, Syntax und/oder Grammatik. 
  

