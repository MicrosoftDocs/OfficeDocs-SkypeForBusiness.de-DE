---
title: "Bereitstellen von Telefonen für Skype for Business Online"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.date: 01/22/2018
ms.topic: article
ms.assetid: faa17eb3-7483-4984-87f2-815d981b68ae
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
description: "Informationen Sie zu den Bereitstellungsschritten, um die richtige Firmware erhalten möchten, aktualisieren sie bei Bedarf, Zuweisen von Lizenzen und Konfigurieren von Einstellungen für Skype für online Business-Telefone"
ms.openlocfilehash: 86756fb1033e2928a7427c9352fbf6fbb24dc154
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2018
---
# <a name="deploying-skype-for-business-online-phones"></a>Bereitstellen von Telefonen für Skype for Business Online

Dieses Bereitstellungshandbuch soll Sie beim Bereitstellen von IP-Telefonen für Skype for Business Online unterstützen.
  
In Unternehmen jeder Art ist eine wichtige Voraussetzung für die Geschäftstätigkeit, dass die Benutzer eine Telefonnummer besitzen, über die sie Sprachanrufe tätigen und empfangen können. Benutzer mit Telefonnummern können Sprachanrufe über alle Skype for Business-Geräte (beispielsweise IP-Telefone, PCs und mobile Geräte) tätigen. Weitere Informationen zu IP-Telefonen für Skype for Business finden Sie unter [Kauf von Telefonen für Skype for Business Online](getting-phones-for-skype-for-business-online.md).
  
## <a name="deployment-steps-for-ip-phones"></a>Bereitstellungsschritte für IP-Telefone

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a>Schritt 1 - Herunterladen der Administratorhandbücher und Telefonhandbücher des Herstellers

Bevor Sie beginnen, sollten Sie die Administratorhandbücher und Telefonhandbücher des Telefonherstellers herunterladen.
  
- Telefone Polycom finden Sie unter [Polycom Bereitstellungshandbuch] ((http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).
    
- Yealink-Telefone: [Yealink-HD-SIP-Telefonlösung für Skype for Business](http://www.yealink.com/products_top_2.html).
    
- AudioCodes-Telefone: [AudioCodes-Handbuch für die Bereitstellungsverwaltung](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a>Schritt 2 - Sicherstellen, dass Sie von Skype for Business unterstützte IP-Telefone und Firmware kaufen oder migrieren

Von Skype for Business Online unterstützte Telefone und Firmware sind auch mit Skype for Business Server kompatibel, umgekehrt ist dies allerdings nicht immer der Fall. Wie Sie sicherstellen, dass Sie unterstützte Telefone und Firmware kaufen oder bereitstellen, erfahren Sie unter [Kauf von Telefonen für Skype for Business Online](getting-phones-for-skype-for-business-online.md).
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a>Schritt 3 - Überprüfen, ob die richtige Firmware installiert ist, und gegebenenfalls Aktualisieren der Firmware

Überprüfen Sie die Firmwareversion Ihrer Telefone:
  
- **Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.
    
- **Yealink-Telefone**: Navigieren Sie auf dem Hauptbildschirm des Telefons zu **Status** (Status).
    
- **AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.
    
    > [!NOTE]
    > Informationen zum Remotezugriff auf Telefondetails finden Sie in den Administratorhandbüchern der Hersteller. Links zu den Benutzer- und Telefonhandbüchern finden Sie weiter oben. 
  
- **Telefone mit Lync Phone Edition (LPE)**: Navigieren Sie vom Startbildschirm aus zu **Menü** > **Systeminformationen**.
    
### <a name="step-4---device-update-considerations"></a>Schritt 4 - Überlegungen zu Geräteupdates

> [!NOTE]
> Polycom-Firmware vor Version 5.5.1.X enthielt einen herstellerspezifischen Mechanismus zum Sperren von Geräten, der durch die Skype for Business-Implementierung „Telefonsperre" ersetzt wird. Beim Upgrade eines mit der „Gerätesperre" gesicherten Telefons von Version 5.4.X.X auf 5.5.1.X mit „Telefonsperre" wird der PIN-Code der „Gerätesperre" nicht vererbt, sodass das Telefon dann möglicherweise ungesichert ist. Benutzer, die die „Gerätesperre" aktiviert haben, müssen den folgenden Parameter im Polycom-Geräteprofil aktivieren, um Benutzern die Kontrolle über den Upgradezeitpunkt zu geben: „lync.deviceUpdate.popUpSK.enabled=1". 
  
Firmwareupdates werden vom Skype for Business-Dienst verwaltet. Die Firmware für alle Skype for Business-zertifizierten Telefone wird auf den Skype for Business-Updateserver hochgeladen, und Geräteupdates sind in allen Telefonen standardmäßig aktiviert. Je nachdem, wann die Telefone inaktiv sind und welche Abrufintervalle festgelegt sind, werden die neuesten zertifizierten Builds automatisch heruntergeladen und installiert. Sie können die Einstellungen für Geräteupdates mit dem [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx)-Cmdlet deaktivieren und den  _EnableDeviceUpdate_-Parameter auf  `false` festlegen.
  
![Deploying phones.](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
Wenn neue Firmware verfügbar und zum Herunterladen und Installieren bereit ist, benachrichtigt das Telefon den Benutzer. Polycom-Telefone benachrichtigen den Benutzer und bieten dabei die Optionen **Update** (Aktualisieren) und **Postpone** (Aufschieben).
  
![Deploying phones.](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
Für Polycom-Telefone können Sie die Firmware auf dem Telefon aktualisieren, indem Sie **SwUpdate** (Softwareupdate) auswählen.
  
![Deploying phones.](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
Wahlweise können Sie Firmwareupdates auch mit einem Partnerbereitstellungssystem verwalten. Informationen zur Verwaltung durch Partnerbereitstellungssysteme einschließlich der erweiterten Telefonanpassung finden Sie in den Administratorhandbüchern der Hersteller.
  
> [!CAUTION]
> Achten Sie darauf, eine einzige Autorität für Geräteupdates (In-Band-Geräteupdate oder Bereitstellungsserver eines Drittanbieters) zu verwenden, um Updateschleifen zu verhindern. 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a>Schritt 5 - Konfiguration und Infrastruktureinstellungen für Telefone

Sie können die am häufigsten verwendeten Telefonoptionen und Richtlinien mithilfe von Windows PowerShell-Cmdlets für die In-Band-Verwaltung von Skype for Business einrichten. Details zu den Parametern und Einstellungen finden Sie unter [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).
  
Informationen zur Planung der Netzwerkinfrastruktur finden Sie unter [Skype Operations Framework](https://www.skypeoperationsframework.com/).
  
### <a name="step-6---preparing-for-users-to-sign-in"></a>Schritt 6 - Vorbereiten der Anmeldung der Benutzer

Damit sich Benutzer erfolgreich bei einem Skype for Business Online-Telefon anmelden und Anrufe tätigen können, müssen Sie sicherstellen, dass den Benutzern die richtigen Lizenzen zugewiesen sind. Sie müssen mindestens eine Telefonsystemlizenz und einen Anrufplan zuweisen. Weitere Informationen sehen Sie [Skype für Geschäfts- und Microsoft-Teams, Add-On-Lizenzierung](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) und [Skype für Geschäfts- und Microsoft-Teams, Lizenzen zuweisen](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).
  
Weitere Informationen zu Anrufplänen finden Sie unter [Was sind Anrufpläne in Office 365?](../../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md).
  
- Verfügbare **Anmeldeoptionen** für Onlinebenutzer:
    
  - Benutzer mit **Polycom VVX 5XX/6XX** -Telefonen sehen folgenden Bildschirm:
    
     ![Deploying phones.](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - Benutzer mit **Yealink T48G/T46G** -Telefonen sehen folgenden Bildschirm:
    
     ![Yealink phones logon.](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    Details zu den von den Herstellern unterstützten Anmeldeoptionen finden Sie unter [Kauf von Telefonen für Skype for Business Online](getting-phones-for-skype-for-business-online.md).
    
- **Benutzer-ID**: Die Benutzer können über die Wähltastatur oder die Bildschirmtastatur (falls verfügbar) des Telefons den Benutzernamen und das Kennwort der Organisation eingeben, um sich bei dem Telefon anzumelden. Für den Benutzernamen müssen sie das UPN-Format verwenden (zum Beispiel *amosm@contoso.com*  ).
    
     ![Deploying phones.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > PIN-Authentifizierung wird für Skype for Business Online in Verbindung mit LPE- und Partner-IP-Telefonen nicht unterstützt. 
  
- **Verwendung eines PCs**: Wenn auf den PCs von Benutzern BToE-Software (Better Together over Ethernet) installiert und aktiviert ist, können sich die Benutzer über das Authentifizierungsfenster in ihrer Skype for Business-App für Windows bei ihrem Telefon anmelden. Weitere Informationen finden Sie unter [Schritt 7 (optional) – Wenn Sie eine Kopplung Gerät und Better Together over Ethernet (BToE) verfügen](deploying-skype-for-business-online-phones.md#BK_BTOE) .
    
    > [!NOTE]
    > Die Benutzer müssen den Benutzernamen und das Kennwort der Organisation eingeben, um sich bei dem Telefon anzumelden. Für den Benutzernamen müssen sie das UPN-Format verwenden (zum Beispiel  *amosm@contoso.com*  ).
  
     ![Deploying phones.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- **Verwendung einer Webanmeldung**: Dies ist eine neue Methode, bei der sich Onlinebenutzer mit einem standardmäßigen Webbrowser authentifizieren können. Den Benutzern werden Anweisungen bereitgestellt, denen sie folgen müssen, wenn sie einen Browser für die Anmeldung verwenden.
    
  - Benutzer mit **Polycom VVX 5XX/6XX** -Telefonen sehen folgenden Bildschirm:
    
     ![Deploying phones.](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - Benutzer mit **Yealink T48G/T46G** -Telefonen sehen folgenden Bildschirm:
    
     ![Yealink phone logon.](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    Der generierte Code läuft nach 15 Minuten ab. Wenn er abgelaufen ist, müssen die Benutzer je nach Telefon auf **Wiederholen** oder **OK** klicken, um einen neuen Code zu generieren.
    
  - Benutzer mit **Polycom VVX 5XX/6XX** -Telefonen sehen folgenden Bildschirm:
    
     ![PIN code expired.](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - Benutzer mit **Yealink T48G/T46G** -Telefonen sehen folgenden Bildschirm:
    
     ![Yealink phones logon.](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    Navigieren Sie in einem Browser zu der auf dem Telefon angezeigten Adresse, und geben Sie Ihren Skype for Business-Benutzernamen ein.
    
     ![Deploying phones.](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    Geben Sie den auf dem Telefon angezeigten Code ein.
    
     ![Deploying phones.](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    Vergewissern Sie sich, dass auf der Website „ **Skype for Business-zertifiziertes Telefon** von [Name des Telefonherstellers]" angezeigt wird, und klicken Sie auf **Weiter**.
    
     ![Deploying phones.](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    Klicken Sie auf die Anmeldeinformationen des Benutzers oder auf **Anderes Konto verwenden**:
    
     ![Deploying phones.](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    Wenn die folgende Seite angezeigt wird, können Sie den Browser gefahrlos schließen.
    
     ![Deploying phones.](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > LPE-Telefone für Skype for Business Online unterstützen nur die Anmeldung über USB-Tethering. 
  
- **Unterstützte Bereitstellungen**: Die folgende Tabelle zeigt die unterstützten Authentifizierungstypen für die zurzeit unterstützten Bereitstellungsmodelle, beispielsweise Exchange-Integration, moderne Authentifizierung mit mehrstufiger Authentifizierung (Multi-factor Authentication, MFA) sowie Skype for Business Online und Skype for Business als lokale Bereitstellung.
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Skype for Business** <br/> |**Exchange** <br/> |**Methode für die Anmeldung beim Telefon** <br/> |**Skype for Business-Zugriff** <br/> |**Exchange-Zugriff mit moderner Authentifizierung und deaktivierter MFA** <br/> |**Exchange-Zugriff mit moderner Authentifizierung und aktivierter MFA** <br/> |
|Online  <br/> |Online  <br/> |Webanmeldung  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |
|Online  <br/> |Online  <br/> |Benutzername/Kennwort  <br/> |Ja  <br/> |Ja  <br/> |Nein  <br/> |
|Online  <br/> |Lokal  <br/> |Webanmeldung  <br/> |Ja  <br/> |Nein  <br/> |Nein  <br/> |
|Online  <br/> |Lokal  <br/> |Benutzername/Kennwort  <br/> |Ja  <br/> |Ja  <br/> |Nein  <br/> |
|Lokal  <br/> |Online/lokal  <br/> |PIN-Authentifizierung  <br/> |Ja  <br/> |Nein  <br/> |Nein  <br/> |
|Lokal  <br/> |Online/lokal  <br/> |Benutzername/Kennwort  <br/> |Ja  <br/> |Ja  <br/> |n/v  <br/> |
|Lokal  <br/> |Online/lokal  <br/> |Anmelden über PC (BToE)  <br/> |Ja  <br/> |Ja  <br/> |n/v  <br/> |
   
- **Telefonfunktionen**: Die Funktionen können sich je nach IP-Telefonpartner geringfügig unterscheiden. Für das vollständige Feature festlegen und Weitere Informationen zu den Features für jeden Hersteller des Telefons, finden Sie unter [Getting Telefone für Skype für Business Online](getting-phones-for-skype-for-business-online.md).
    
- Die **Telefonsperre** ist eine kürzlich eingeführte Funktion von Skype for Business-zertifizierten Telefonen, mit der Telefone gesichert werden können. Wenn die Funktion aktiviert ist, werden die Benutzer aufgefordert, nach der erfolgreichen Authentifizierung eine PIN zu erstellen. Nach der Erstellung der PIN werden die Telefone gesperrt, wenn das von Ihnen definierte Leerlauftimeout abgelaufen ist, Benutzer ihr Telefon manuell sperren oder ihre Telefonsperre über die Telefonkopplung mit ihrem PC synchronisieren. Wenn die PIN für die Telefonsperre mehrmals falsch eingegeben wird, wird der Benutzer entweder abgemeldet oder das Telefon muss mit einem Administratorcode entsperrt werden. Dies ist jedoch je nach Telefonpartner unterschiedlich. Die PIN des Benutzers muss aus 6 bis 15 Ziffern bestehen.
    
    Sie können die standardmäßig aktivierte Telefonsperre für Ihre Organisation deaktivieren, das Leerlauftimeout ändern und mithilfe von In-Band-Einstellungen auswählen, ob Benutzer trotz der Sperre Telefonanrufe tätigen können. Weitere Details zu diesen Einstellungen finden Sie unter [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a>Schritt 7 (optional) - Wenn Sie Gerätekopplung und Better Together over Ethernet (BToE) verwenden
<a name="BK_BTOE"> </a>

BToE ist ein Telefonkopplungsmechanismus für Partner-IP-Telefone, bei dem die Telefone der Benutzer mit ihrer Skype for Business-App für Windows gekoppelt werden. BToE bietet den Benutzern folgende Möglichkeiten:
  
- Anmelden bei ihrem IP-Telefon über die Skype for Business-Desktop-App (auf einem PC)
    
- Synchronisieren der Telefonsperre mit der PC-Sperre
    
- Anruf per Mausklick
    
BToE kann für den Betrieb in zwei Modi konfiguriert werden:  *Automatisch*  (Standard) und *Manuell*  . Außerdem kann es mit In-Band-Einstellungen von Skype for Business für Benutzer aktiviert (Standard) oder deaktiviert werden. Im Betrieb im Modus *Manuell*  müssen die Benutzer einen zusätzlichen Schritt ausführen, um ihr Telefon mit der Windows-App zu koppeln.
  
 **So stellen Sie BToE für Benutzer bereit**
  
1. Verbinden Sie den PC über den PC-Anschluss mit dem Telefon.
    
     ![Deploying phones.](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. Laden Sie über die folgenden Links die neueste BToE-Software von der Website des entsprechenden Herstellers herunter. Sie können die Benutzerfreundlichkeit erhöhen, indem Sie die BToE-Software mit einer Administratorverteilungslösung wie System Center Configuration Manager (SCCM) verteilen und installieren. Hilfe zur Verwendung von SCCM finden Sie unter [Pakete und Programme in System Center Configuration Manager](https://docs.microsoft.com/en-us/sccm/apps/deploy-use/packages-and-programs).
    
  - [Polycom-Downloadwebsite für BToE-Software](http://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
  - [Yealink-Downloadwebsite für BToE-Software](http://www.yealink.com/products_list_10.html)
    
  - [AudioCodes-Downloadwebsite für BToE-Software](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. Die Servereinstellung für BToE ist standardmäßig auf **Aktiviert** und **Automodus** festgelegt. Um diese Einstellungen zu ändern, finden Sie unter [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).
    
> [!NOTE]
> BToE wird zurzeit auf Mac- und VDI-Plattformen nicht unterstützt. 
  
## <a name="related-topics"></a>Verwandte Themen
[Anfordern von Servicenummern für Skype for Business und Microsoft Teams](../../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[Das bietet Ihnen das Telefonsystem in Office 365](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system.md)

[Verfügbarkeit von Land und Region für Audiokonferenz und Anrufpläne](../../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)


