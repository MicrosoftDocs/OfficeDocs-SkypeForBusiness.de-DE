---
title: "Konfigurieren der Länge der PIN für Einwahl-Besprechungen"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/15/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
description: "Learn the parameters for the length and requirements of a PIN and see how to set the length for meetings in Skype for Business."
---

# Konfigurieren der Länge der PIN für Einwahl-Besprechungen

Bei der Konfiguration von Einwahlkonferenzen in Skype for Business Online erhalten Sie Telefonnummern sowie eine so genannte Einwahl- oder Audiokonferenzbrücke. Eine Konferenzbrücke kann eine oder mehr Telefonnummern umfassen. Die von Ihnen eingerichtete Telefonnummer wird in der Besprechungseinladung angegeben.
  
Die Einwahl- oder Audiokonferenzbrücke nimmt den Anruf eines Benutzers an, der sich mit einem Telefon in eine Besprechung einwählt. Sie nimmt den Anruf an und gibt Sprachansagen einer automatischen Telefonzentrale aus. Je nach den von Ihnen festgelegten Einstellungen kann sie dann Benachrichtigungen wiedergeben und Anrufer zur Aufnahme ihres Namens auffordern. In den Einstellungen von Microsoft Bridge in Skype for Business Online können Sie die Einstellungen für Benachrichtigungen für Besprechungen und die Besprechungsteilnahme ändern und die Länge der PINs festlegen, die von Organisatoren von Besprechungen verwendet werden. Die Organisatoren der Besprechung verwenden PINs, um eine Besprechung zu starten.
  
## Konfigurieren der PIN-Länge

### PIN-Länge für Organisatoren von Besprechungen festlegen

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.
    
3. Rufen Sie in der linken Navigationsleiste des **Skype for Business Admin Center** ** Einwahlkonferenzen** > **Einstellungen von Microsoft Bridge** auf.
    
4. Geben Sie unter **Sicherheit** > **PIN-Länge** die gewünschte Anzahl der Ziffern für die PIN ein und klicken Sie auf **Speichern**.
    
> [!NOTE]
> Eine PIN hat nichts mit einer Konferenz-ID zu tun. Konferenz-IDs werden von Anrufern bei der Teilnahme an einer Besprechung verwendet. Sie dienen der Kennzeichnung der Besprechung. Anhand der PIN wird ein Anrufer als Organisator der Besprechung authentifiziert. 
  
## Möchten Sie mehr über PIN-Einstellungen erfahren?

- PINs können 4 bis 12 Ziffern enthalten, standardmäßig werden 5 Ziffern verwendet. PINs können nur Zahlen umfassen. Buchstaben und Sonderzeichen sind nicht zulässig.
    
- Der Organisator der Besprechung benötigt eine PIN, falls die Besprechung noch nicht von einem Benutzer eines Skype for Business-Clients gestartet wurde. Wenn sich alle Teilnehmer in die Besprechung einwählen, ist die PIN erforderlich, damit der Organisator der Besprechung die Besprechung starten kann.
    
- Die PIN-Sicherheitseinstellungen gelten für alle Telefonnummern, die zu einer Microsoft-Brücke gehören. Sie gelten für alle Besprechungen, bei denen zu einer bestimmten Audiokonferenzbrücke gehörende Telefonnummern genutzt werden.
    
## Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Set-CsOnlineDialInConferencingTenantSettings](http://go.microsoft.com/fwlink/?LinkId=715757) nutzen.
    
- So stellen Sie die Anzahl der Ziffern in der PIN auf 8 Ziffern ein:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`
    
- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Sechs Gründe für die Verwendung von Windows PowerShell zur Verwaltung von Office 365 ](http://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell bietet gegenüber einer alleinigen Verwendung von Office 365 Admin Center in Bezug auf Geschwindigkeit, Einfachheit und Produktivität unzählige Vorteile, z. B. wenn Sie die Einstellungen für viele Benutzer gleichzeitig ändern. In den folgenden Themen erfahren Sie mehr über diese Vorteile:
    
  - [Eine Einführung in Windows PowerShell und Skype for Business Online](http://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](http://go.microsoft.com/fwlink/?LinkId=525453)
    
    [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](http://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](http://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](http://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
  
## Siehe auch

#### Weitere Ressourcen

[Einwahlkonferenzen in Office 365](../misctopics/dial-in-conferencing-in-office-365.md)

