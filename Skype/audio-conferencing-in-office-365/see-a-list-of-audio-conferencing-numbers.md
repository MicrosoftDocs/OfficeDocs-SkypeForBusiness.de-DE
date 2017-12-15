---
title: "Anzeigen einer Liste mit Einwahlnummern für Einwahlkonferenzen"
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
- Strat_SB_PSTN
ms.assetid: 2d6b4ed4-e12b-4691-8405-fae720d69425
description: "Learn how to look up your dial-in conferencing numbers from within Skype for Business. "
---

# Anzeigen einer Liste mit Einwahlnummern für Einwahlkonferenzen

Wenn Sie Einwahlkonferenzen in Skype for Business Online einrichten, können Sie die für Ihre Benutzer bei Einwahlkonferenzen verfügbaren Telefonnummern anzeigen. Diese Liste enthält alle Einwahlkonferenz-Telefonnummern, die für Ihre Organisation verfügbar sind. Es wird nicht jede für Einwahlkonferenzen verfügbare Telefonnummer aufgelistet, Sie können jedoch durch Klicken auf [Telefonnummern für Audiokonferenzen](phone-numbers-for-audio-conferencing.md) die Länder/Regionen anzeigen, in denen Telefonnummern für Einwahlkonferenzen verfügbar sind.
  
Wenn für Ihre Organisation nur eine Telefonnummer verfügbar ist, wird sie als Standardtelefonnummer für alle Benutzer verwendet. Wenn mehrere Telefonnummern verfügbar sind, können Sie für jeden Benutzer eine Standardtelefonnummer auswählen. Diese Standardnummer ist in den Einladungen für Besprechungen über Skype for Business Online angegeben.
  
Weitere Informationen zum Ändern der Einwahl-Telefonnummer für einen Benutzer finden Sie unter [Festlegen der in Einladungen enthaltenen Audiokonferenz-Telefonnummern für Besprechungsorganisatoren](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md).
  
> [!NOTE]
> Inländische Einwahlnummern sind Ihrer Organisation zugeordnet. Nur solche Nummern können als Standardtelefonnummer eingestellt werden. Internationale Einwahlnummern können von mehreren Organisationen gemeinsam verwendet werden. 
  
## So zeigen Sie Ihre Einwahlnummern für Einwahlkonferenzen an:

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.
    
3. Schalten Sie in **Skype for Business Admin Center** in der linken Navigationsleiste zu **Einwahlkonferenz** > **Microsoft Bridge**. Nächster Schritt:
    
  - Sie können die Telefonnummern anzeigen, die zur Verwendung für Einwahlkonferenzen verfügbar sind.
    
  - Sie können zudem den Standort sowie die primären und sekundären Sprachen anzeigen, die von der automatischen Telefonzentrale für Einwahlkonferenzen verwendet werden.
    
> [!NOTE]
> Sie können unter **Einwahlkonferenzen** > **Benutzer mit eingehenden Verbindungen** die Eigenschaften des Benutzers auswählen und die Standardtelefonnummer ändern. Wählen Sie dazu eine neue Nummer aus der Liste der für Ihr Unternehmen verfügbaren Telefonnummern aus. Siehe[Festlegen der in Einladungen enthaltenen Audiokonferenz-Telefonnummern für Besprechungsorganisatoren](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md). 
  
## Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Get-CsOnlineDialInConferencingServiceNumber](http://go.microsoft.com/fwlink/?LinkId=617691) nutzen.
    
- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Sechs Gründe für die Verwendung von Windows PowerShell zur Verwaltung von Office 365 ](http://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell bietet gegenüber einer alleinigen Verwendung von Office 365 Admin Center in Bezug auf Geschwindigkeit, Einfachheit und Produktivität unzählige Vorteile, z. B. wenn Sie die Einstellungen für viele Benutzer gleichzeitig ändern. In den folgenden Themen erfahren Sie mehr über diese Vorteile:
    
  - [Eine Einführung in Windows PowerShell und Skype for Business Online](http://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](http://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](http://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](http://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
  
## Siehe auch

#### Weitere Ressourcen

[Einwahlkonferenzen in Office 365](../misctopics/dial-in-conferencing-in-office-365.md)

