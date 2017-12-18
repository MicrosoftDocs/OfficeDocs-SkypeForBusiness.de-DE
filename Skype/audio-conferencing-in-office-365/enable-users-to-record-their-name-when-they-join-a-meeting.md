---
title: "Aktivieren der Aufzeichnung des Benutzernamens beim Beitreten einer Besprechung"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/12/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
description: "Learn how to enable or disable whether your users can record their names when they join a meeting "
---

# Aktivieren der Aufzeichnung des Benutzernamens beim Beitreten einer Besprechung

> [!IMPORTANT]
> Dieser Artikel wurde maschinell übersetzt. Bitte beachten Sie den [Haftungsausschluss](1d649328-ada7-422d-a074-d6da4da36970.md#MT_Footer).  
  
Wenn Sie einen Audiokonferenzanbieter für Skype for Business und Microsoft Teams einrichten, erhalten Sie Telefonnummern und was eine audio Konferenzbrücke aufgerufen wird. Eine Konferenzbrücke kann eine oder mehrere Telefonnummern enthalten, die eine dedizierte oder freigegebene Telefonnummer werden können.
  
Die Konferenzbrücke nimmt den Anruf eines Benutzers an, der sich mit einem Telefon in eine Besprechung einwählt. Die Konferenzbrücke nimmt den Anruf an und gibt Sprachansagen einer automatischen Telefonzentrale aus. Je nach den festgelegten Einstellungen gibt sie Benachrichtigungen wieder und fordert Anrufer auf, ihren Namen aufzuzeichnen. Zudem richtet sie die PIN-Sicherheit für die Organisatoren der Besprechung ein. Der Organisator der Besprechung erhält PINs, damit er eine Besprechung starten kann. Sie können in Ihren Einstellungen jedoch festlegen, dass zum Start einer Besprechung keine PIN erforderlich ist.
  
## Festlegen, ob Anrufer ihren Namen aufzeichnen sollen

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.
    
3. Wechseln Sie in der **Skype for Business Admin Center**, in der linken Navigation zu **Konferenzen Audio** > **Microsoft Bridge Einstellungen**.
    
4. Unter **Teilnahme an Besprechungen** > **Aktivieren von Nachrichten für Eintritt in und Abgang aus einer Besprechung einschalten**
    
  - **Aktivierte** Anrufer werden aufgefordert, ihren Namen aufzuzeichnen, bevor sie an der Besprechung teilnehmen. Diese Option ist standardmäßig aktiviert.
    
  - **Nicht aktivierte** Anrufer werden nicht aufgefordert, ihren Namen aufzuzeichnen, bevor sie an der Besprechung teilnehmen.
    
5. Nachdem Sie die Änderungen vorgenommen haben, klicken Sie auf **Speichern**.
    
## Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Wenn Sie Zeit sparen, oder dies automatisieren, können Sie das Cmdlet " [Set-CsOnlineDialInConferencingTenantSettings ](https://go.microsoft.com/fwlink/?LinkId=715757) " verwenden.
    
- Windows PowerShell ist alles über die Verwaltung von Benutzern und welche Benutzer berechtigt sind. Mit Windows PowerShell können Sie Office 365 mit einer zentrale Verwaltung, die Ihre tägliche Arbeit vereinfachen können, wenn Sie mehrere Aufgaben ausführen haben verwalten. Um mit Windows PowerShell anzufangen, finden Sie unter folgenden Themen:
    
  - [Sechs Gründe für die Verwendung von Windows PowerShell zur Verwaltung von Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell bietet gegenüber einer alleinigen Verwendung von Office 365 Admin Center in Bezug auf Geschwindigkeit, Einfachheit und Produktivität unzählige Vorteile, z. B. wenn Sie die Einstellungen für viele Benutzer gleichzeitig ändern. In den folgenden Themen erfahren Sie mehr über diese Vorteile:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Haftungsausschluss für maschinelle Übersetzungen**: Dieser Artikel wurde mithilfe eines Computersystems und ohne jegliche Bearbeitung durch Personen übersetzt. Microsoft bietet solche maschinellen Übersetzungen als Hilfestellung für Benutzer ohne Englischkenntnisse an, damit Sie von den Informationen zu Produkten, Diensten und Technologien von Microsoft profitieren können. Da es sich bei diesem Artikel um eine maschinelle Übersetzung handelt, enthält er möglicherweise Fehler in Bezug auf (Fach-)Terminologie, Syntax und/oder Grammatik. 
  
## Siehe auch
<a name="MT_Footer"> </a>

#### Weitere Ressourcen

[Einwahlkonferenzen in Office 365](../misctopics/dial-in-conferencing-in-office-365.md)

