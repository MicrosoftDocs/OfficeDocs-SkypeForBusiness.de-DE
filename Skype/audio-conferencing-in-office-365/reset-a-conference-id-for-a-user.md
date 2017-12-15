---
title: "Einrichten einer Konferenz-ID für einen Benutzer"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- httpsfix
- Strat_SB_PSTN
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
description: "Learn the steps to reset a user's meeting conference ID, and get links to meeting update and migration tools. "
---

# Einrichten einer Konferenz-ID für einen Benutzer

Wenn Ihre Organisation nicht für dynamische Konferenz-IDs aktiviert ist, wird automatisch eine statische Konferenz-ID erstellt, wenn ein Benutzer unter Verwendung von Microsoft als Anbieter für Einwahlkonferenzen aktiviert wird. Diese Konferenz-ID und die Einwahltelefonnummern, über die sich Benutzer in eine Besprechung einwählen können, sind unten in den Besprechungseinladungen von Skype for Business Online aufgeführt. Wenn der Benutzer diese Telefonnummer wählt, wird er von der automatischen Telefonzentrale aufgefordert, diese Konferenz-ID einzugeben, damit er an der Besprechung teilnehmen kann.
  
Feste Nummern werden verwendet, wenn sich die Mitarbeiter Ihres Unternehmens keine Zufallszahlenkombinationen merken möchten und es bevorzugen, eine bestimmte bzw. leicht zu merkende Nummer auszuwählen. Bei der Verwendung von dynamischen Konferenz-IDs wird für jede, vom Benutzer geplante Besprechung, eine eindeutige Konferenz-ID zugewiesen. Wenn Sie dynamische Konferenz-IDs zuweisen möchten, klicken Sie [Verwenden von Audiokonferenzanbieter dynamische IDs in Ihrer Organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md).
  
Konferenz-IDs werden nur von Skype for Business automatisch für die Benutzer festgelegt, die mit Microsoft als Anbieter von Einwahlkonferenzen für Einwahlkonferenzen aktiviert wurden. Falls Sie eine Konferenz-ID für einen Benutzer zurücksetzen müssen, der einen externen Audiokonferenzanbieter (ACP) nutzt, müssen Sie die Konferenz-ID auf der Seite der Benutzereigenschaften für den entsprechenden Benutzer manuell eingeben.
  
## Konferenz-ID der Besprechung für einen Benutzer zurücksetzen

### Zurücksetzen der Konferenz-ID der Besprechung

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.
    
3. Klicken Sie im **Skype for Business Admin Center**auf **Einwahlkonferenzen** und dann im Bereich „Aktion" unter **Konferenz-ID** auf **Zurücksetzen**.
    
4. Klicken Sie im Fenster **Konferenz-ID zurücksetzen?** auf **Ja**. Daraufhin wird automatisch eine neue Konferenz-ID generiert und per E-Mail an den Benutzer geschickt. Standardmäßig werden E-Mails an die Benutzer gesendet. Dieses Verhalten kann aber ausgeschaltet werden. 
    
    > [!NOTE]
    > Nach dem Zurücksetzen der Konferenz-ID wird die neue Konferenz-ID per E-Mail an den Benutzer geschickt. Diese E-Mail wird an die Haupt-E-Mail-Adresse geschickt. Dabei handelt es sich oftmals um das Office 365-Postfach. Die E-Mail umfasst die neue Konferenz-ID, die Standardeinwahlnummer(n) und Anweisungen, wie bestehende Besprechungen mithilfe des Skype for Business Meeting Update Tool aktualisiert werden können. 
  
## Was sollte ich noch wissen?

- Sie können dem Benutzer eine E-Mail mit sämtlichen Informationen zur Konferenz schicken, u. a. mit der Konferenz-ID und den Einwahlnummern. Klicken Sie dazu auf **Konferenzinformationen per E-Mail senden**. Die PIN wird nicht gesendet.
    
- Eine Konferenz-ID umfasst 7 Ziffern. Die Länge kann weder im Skype for Business Admin Center noch mit der Windows PowerShell geändert werden.
    
- Nach dem Zurücksetzen wird die neue Konferenz-ID unter **Konferenz-ID** aufgeführt.
    
- Die Konferenz-ID für Einwahlkonferenzen für einen Benutzer wird unten im Bereich „Aktion" unter **Einwahlkonferenzen** angezeigt, wenn Sie auf der Seite **Benutzer** einen Benutzer auswählen.
    
- Nachdem eine neue Konferenz-ID generiert wurde, können Anrufer die alte Konferenz-ID nicht mehr verwenden. Sie sollten Benutzer benachrichtigen, dass sie ihre angesetzten Besprechungseinladungen neu planen, damit die neue Konferenz-ID den Einladungen hinzugefügt wird. Die Benutzer können angesetzte Besprechungen mithilfe des Skype for Business Meeting Update Tool aktualisieren. Informationen zum Download, zur Installation und zum Ausführen des Skype for Business Meeting Update Tool finden Sie unter:
    
  - [Skype for Business (Lync) Meeting Update Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [Skype for Business Online, Meeting Migration Tool (64 Bit)](http://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [Skype for Business Online, Meeting Migration Tool (32 Bit)](http://go.microsoft.com/fwlink/?LinkID=626046)
    
## Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- In Bezug auf Windows PowerShell geht es um das Verwalten von Benutzern und darum, was Benutzer tun dürfen und was nicht. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online zentral verwalten. Dies kann Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Aufgaben ausführen müssen. Informationen zu den ersten Schritten mit Windows PowerShell finden Sie unter den folgenden Themen:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sechs Gründe für die Verwendung von Windows PowerShell zum Verwalten von Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell zum Ausführen häufiger Skype for Business Online-Verwaltungsaufgaben](https://go.microsoft.com/fwlink/?LinkId=525038)
    

