---
title: Bereitstellen von Telefonen für Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: faa17eb3-7483-4984-87f2-815d981b68ae
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Phone System
description: Lernen Sie die Bereitstellungsschritte kennen, um die richtige Firmware zu erhalten, sie bei Bedarf zu aktualisieren, Lizenzen zuzuweisen und Einstellungen für Telefone für Skype for Business Online zu konfigurieren.
ms.openlocfilehash: 4237e1cb32204a3d87d639710a2829c1111cc354
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780062"
---
# <a name="deploying-skype-for-business-online-phones"></a><span data-ttu-id="2ca31-103">Bereitstellen von Telefonen für Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="2ca31-103">Deploying Skype for Business Online phones</span></span>

<span data-ttu-id="2ca31-104">Dieses Bereitstellungshandbuch soll Sie beim Bereitstellen von IP-Telefonen für Skype for Business Online unterstützen.</span><span class="sxs-lookup"><span data-stu-id="2ca31-104">This is deployment guide will help you deploy Skype for Business Online IP phones.</span></span>
  
<span data-ttu-id="2ca31-p101">In Unternehmen jeder Art ist eine wichtige Voraussetzung für die Geschäftstätigkeit, dass die Benutzer eine Telefonnummer besitzen, über die sie Sprachanrufe tätigen und empfangen können. Benutzer mit Telefonnummern können Sprachanrufe über alle Skype for Business-Geräte (beispielsweise IP-Telefone, PCs und mobile Geräte) tätigen. Weitere Informationen zu IP-Telefonen für Skype for Business finden Sie unter [Kauf von Telefonen für Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="2ca31-p101">In all types of businesses, having a phone number allows users to make and get voice calls, and it is an important requirement to do business. Users who have phone numbers will be able to make voice calls across all Skype for Business devices including IP phones, PCs, and mobile devices. You can learn more about Skype for Business IP phones by reading [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
## <a name="deployment-steps-for-ip-phones"></a><span data-ttu-id="2ca31-108">Bereitstellungsschritte für IP-Telefone</span><span class="sxs-lookup"><span data-stu-id="2ca31-108">Deployment steps for IP phones</span></span>

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a><span data-ttu-id="2ca31-109">Schritt 1 - Herunterladen der Administratorhandbücher und Telefonhandbücher des Herstellers</span><span class="sxs-lookup"><span data-stu-id="2ca31-109">Step 1 - Download the manufacturer's administrator guides and phone manuals</span></span>

<span data-ttu-id="2ca31-110">Bevor Sie beginnen, sollten Sie die Administratorhandbücher und Telefonhandbücher des Telefonherstellers herunterladen.</span><span class="sxs-lookup"><span data-stu-id="2ca31-110">Before you get started, it's a good idea to download the phone manufacturer's administration guides and phone user manuals.</span></span>
  
- <span data-ttu-id="2ca31-111">Für Polycom-Telefone finden Sie weitere Informationen unter [Polycom Deployment Guide] ((http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).</span><span class="sxs-lookup"><span data-stu-id="2ca31-111">For Polycom phones, see the http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).</span></span>
    
- <span data-ttu-id="2ca31-112">Yealink-Telefone: [Yealink-HD-SIP-Telefonlösung für Skype for Business](http://www.yealink.com/products_top_2.html).</span><span class="sxs-lookup"><span data-stu-id="2ca31-112">For Yealink phones, see [Yealink Skype for Business HD SIP Phones Solution](http://www.yealink.com/products_top_2.html).</span></span>
    
- <span data-ttu-id="2ca31-113">AudioCodes-Telefone: [AudioCodes-Handbuch für die Bereitstellungsverwaltung](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).</span><span class="sxs-lookup"><span data-stu-id="2ca31-113">For AudioCodes phones, see the [Audiocodes Provisioning Management Guide](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).</span></span>
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a><span data-ttu-id="2ca31-114">Schritt 2 - Sicherstellen, dass Sie von Skype for Business unterstützte IP-Telefone und Firmware kaufen oder migrieren</span><span class="sxs-lookup"><span data-stu-id="2ca31-114">Step 2 - Make sure you're purchasing or migrating a Skype for Business Supported IP phone and firmware</span></span>

<span data-ttu-id="2ca31-p102">Von Skype for Business Online unterstützte Telefone und Firmware sind auch mit Skype for Business Server kompatibel, umgekehrt ist dies allerdings nicht immer der Fall. Wie Sie sicherstellen, dass Sie unterstützte Telefone und Firmware kaufen oder bereitstellen, erfahren Sie unter [Kauf von Telefonen für Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="2ca31-p102">A Skype for Business Online supported phone and firmware is compatible for Skype for Business Server as well, but the opposite isn't always true. To make sure you are buying or provisioning a supported phone and firmware, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a><span data-ttu-id="2ca31-117">Schritt 3 - Überprüfen, ob die richtige Firmware installiert ist, und gegebenenfalls Aktualisieren der Firmware</span><span class="sxs-lookup"><span data-stu-id="2ca31-117">Step 3 - Checking that the right firmware is installed and update the firmware if required</span></span>

<span data-ttu-id="2ca31-p103">Überprüfen Sie die Firmwareversion Ihrer Telefone:</span><span class="sxs-lookup"><span data-stu-id="2ca31-p103">Check the firmware version on your phones. For:</span></span>
  
- <span data-ttu-id="2ca31-120">Für **Polycom VVX-Telefone**, gehen Sie auf **Einstellungen** > **Status** > **Plattform** > **Anwendung** > **Main**.</span><span class="sxs-lookup"><span data-stu-id="2ca31-120">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
    
- <span data-ttu-id="2ca31-121">**Yealink-Telefone**: Navigieren Sie auf dem Hauptbildschirm des Telefons zu **Status** (Status).</span><span class="sxs-lookup"><span data-stu-id="2ca31-121">**Yealink phones**, go to **Status** on the main phone screen.</span></span>
    
- <span data-ttu-id="2ca31-122">Für **AudioCodes-Telefone**, gehen Sie auf dem Hauptbildschirm auf **Menü** > **Gerätestatus** > **Firmware-Version**.</span><span class="sxs-lookup"><span data-stu-id="2ca31-122">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2ca31-p104">Informationen zum Remotezugriff auf Telefondetails finden Sie in den Administratorhandbüchern der Hersteller. Links zu den Benutzer- und Telefonhandbüchern finden Sie weiter oben.</span><span class="sxs-lookup"><span data-stu-id="2ca31-p104">For remote access to phone details, refer to manufacturer administration guides. See the links above for the user guides and phone manuals.</span></span> 
  
- <span data-ttu-id="2ca31-125">**Telefone mit Lync Phone Edition (LPE)**: Navigieren Sie vom Startbildschirm aus zu **Menü** > **Systeminformationen**.</span><span class="sxs-lookup"><span data-stu-id="2ca31-125">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span></span>
    
### <a name="step-4---device-update-considerations"></a><span data-ttu-id="2ca31-126">Schritt 4 - Überlegungen zu Geräteupdates</span><span class="sxs-lookup"><span data-stu-id="2ca31-126">Step 4 - Device Update Considerations</span></span>

> [!NOTE]
> <span data-ttu-id="2ca31-p105">Polycom-Firmware vor Version 5.5.1.X enthielt einen herstellerspezifischen Mechanismus zum Sperren von Geräten, der durch die Skype for Business-Implementierung „Telefonsperre" ersetzt wird. Beim Upgrade eines mit der „Gerätesperre" gesicherten Telefons von Version 5.4.X.X auf 5.5.1.X mit „Telefonsperre" wird der PIN-Code der „Gerätesperre" nicht vererbt, sodass das Telefon dann möglicherweise ungesichert ist. Benutzer, die die „Gerätesperre" aktiviert haben, müssen den folgenden Parameter im Polycom-Geräteprofil aktivieren, um Benutzern die Kontrolle über den Upgradezeitpunkt zu geben: „lync.deviceUpdate.popUpSK.enabled=1".</span><span class="sxs-lookup"><span data-stu-id="2ca31-p105">Polycom firmware prior to 5.5.1.X had a manufacturer-specific device-lock mechanism that is replaced with a Skype for Business implementation "Phone-Lock." Upgrading a phone from 5.4.X.X that was secured with "Device-Lock" to 5.5.1.X with "Phone-Lock" won't inherit the PIN code from "Device-Lock," which can leave the phone unsecured. Users who have activated "Device-Lock" need to enable the following Polycom Device Profile parameter to give users control of time of upgrade (lync.deviceUpdate.popUpSK.enabled=1).</span></span> 
  
<span data-ttu-id="2ca31-p106">Firmwareupdates werden vom Skype for Business-Dienst verwaltet. Die Firmware für alle Skype for Business-zertifizierten Telefone wird auf den Skype for Business-Updateserver hochgeladen, und Geräteupdates sind in allen Telefonen standardmäßig aktiviert. Je nachdem, wann die Telefone inaktiv sind und welche Abrufintervalle festgelegt sind, werden die neuesten zertifizierten Builds automatisch heruntergeladen und installiert. Sie können die Einstellungen für Geräteupdates mit dem [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx)-Cmdlet deaktivieren und den  _EnableDeviceUpdate_-Parameter auf  `false` festlegen.</span><span class="sxs-lookup"><span data-stu-id="2ca31-p106">Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default. Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.</span></span>
  
![Bereitstellen von Telefonen.](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
<span data-ttu-id="2ca31-p107">Wenn neue Firmware verfügbar und zum Herunterladen und Installieren bereit ist, benachrichtigt das Telefon den Benutzer. Polycom-Telefone benachrichtigen den Benutzer und bieten dabei die Optionen **Update** (Aktualisieren) und **Postpone** (Aufschieben).</span><span class="sxs-lookup"><span data-stu-id="2ca31-p107">When a new firmware is available and ready for download and install, the phone will notify the user. Polycom phones will notify the user and provide them with an option to **Update** or **Postpone**.</span></span>
  
![Bereitstellen von Telefonen.](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
<span data-ttu-id="2ca31-138">Für Polycom-Telefone können Sie die Firmware auf dem Telefon aktualisieren, indem Sie **SwUpdate** (Softwareupdate) auswählen.</span><span class="sxs-lookup"><span data-stu-id="2ca31-138">For a Polycom phone, you can update the firmware on the phone by selecting **SwUpdate**.</span></span>
  
![Bereitstellen von Telefonen.](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
<span data-ttu-id="2ca31-p108">Wahlweise können Sie Firmwareupdates auch mit einem Partnerbereitstellungssystem verwalten. Informationen zur Verwaltung durch Partnerbereitstellungssysteme einschließlich der erweiterten Telefonanpassung finden Sie in den Administratorhandbüchern der Hersteller.</span><span class="sxs-lookup"><span data-stu-id="2ca31-p108">You can also choose to manage firmware updates using a partner provisioning system. For partner provisioning system management including advanced phone customization, refer to manufacturer administration guides.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="2ca31-142">Achten Sie darauf, eine einzige Autorität für Geräteupdates (In-Band-Geräteupdate oder Bereitstellungsserver eines Drittanbieters) zu verwenden, um Updateschleifen zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="2ca31-142">Make sure to have a single device update authority (In-band device update or a third-party provisioning server) to avoid update loops.</span></span> 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a><span data-ttu-id="2ca31-143">Schritt 5 - Konfiguration und Infrastruktureinstellungen für Telefone</span><span class="sxs-lookup"><span data-stu-id="2ca31-143">Step 5 - Configuration and infrastructure phone settings</span></span>

<span data-ttu-id="2ca31-p109">Sie können die am häufigsten verwendeten Telefonoptionen und Richtlinien mithilfe von Windows PowerShell-Cmdlets für die In-Band-Verwaltung von Skype for Business einrichten. Details zu den Parametern und Einstellungen finden Sie unter [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).</span><span class="sxs-lookup"><span data-stu-id="2ca31-p109">You can set up the most commonly used phone options and policies using Skype for Business In-band management Windows PowerShell cmdlets. See [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) for details of those parameters and settings.</span></span>
  
<span data-ttu-id="2ca31-146">Informationen zur Planung der Netzwerkinfrastruktur finden Sie unter [Skype Operations Framework](https://www.skypeoperationsframework.com/).</span><span class="sxs-lookup"><span data-stu-id="2ca31-146">For network infrastructure planning, see [Skype Operations Framework](https://www.skypeoperationsframework.com/).</span></span>
  
### <a name="step-6---preparing-for-users-to-sign-in"></a><span data-ttu-id="2ca31-147">Schritt 6 - Vorbereiten der Anmeldung der Benutzer</span><span class="sxs-lookup"><span data-stu-id="2ca31-147">Step 6 - Preparing for users to sign in</span></span>

<span data-ttu-id="2ca31-p110">Damit sich Benutzer erfolgreich bei einem Skype for Business Online-Telefon anmelden und Anrufe tätigen können, müssen Sie sicherstellen, dass den Benutzern die richtigen Lizenzen zugewiesen sind. Sie müssen mindestens eine Telefonsystemlizenz und einen Anrufplan zuweisen. Weitere Informationen finden Sie unter [Add-On-Lizenzierung für Skype for Business und Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) und[Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="2ca31-p110">To enable users to successfully sign in to a Skype for Business Online phone and make calls, you need to make sure users are assigned the correct licenses. At a minimum, you will need to assign a Phone System license and a Calling Plan. For additional information, you can see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) and[Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
  
<span data-ttu-id="2ca31-151">Weitere Informationen zu Anrufplänen finden Sie unter [Was sind Anrufpläne in Office 365?](/microsoftteams/what-are-calling-plans-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="2ca31-151">You can find out more about Calling Plans by reading [What are Calling Plans in Office 365?](/microsoftteams/what-are-calling-plans-in-office-365)</span></span>
  
- <span data-ttu-id="2ca31-152">Verfügbare **Anmeldeoptionen** für Onlinebenutzer:</span><span class="sxs-lookup"><span data-stu-id="2ca31-152">**Sign-in options** that are available for Online users are:</span></span>
    
  - <span data-ttu-id="2ca31-153">Benutzer mit **Polycom VVX 5XX/6XX** -Telefonen sehen folgenden Bildschirm:</span><span class="sxs-lookup"><span data-stu-id="2ca31-153">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Bereitstellen von Telefonen.](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - <span data-ttu-id="2ca31-155">Benutzer mit **Yealink T48G/T46G** -Telefonen sehen folgenden Bildschirm:</span><span class="sxs-lookup"><span data-stu-id="2ca31-155">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Yealink-Telefon-Login.](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    <span data-ttu-id="2ca31-157">Details zu den von den Herstellern unterstützten Anmeldeoptionen finden Sie unter [Kauf von Telefonen für Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="2ca31-157">For details on sign-in options supported by the manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="2ca31-p111">**Benutzer-ID**: Die Benutzer können über die Wähltastatur oder die Bildschirmtastatur (falls verfügbar) des Telefons den Benutzernamen und das Kennwort der Organisation eingeben, um sich bei dem Telefon anzumelden. Für den Benutzernamen müssen sie das UPN-Format verwenden (zum Beispiel *amosm@contoso.com*  ).</span><span class="sxs-lookup"><span data-stu-id="2ca31-p111">**User ID** Using the phone's keypad or on-screen keyboard (if available), users can use their organization's user name and password to sign in to the phone. For example, they should use the UPN format like *amosm@contoso.com*  for their user name.</span></span>
    
     ![Bereitstellen von Telefonen.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > <span data-ttu-id="2ca31-161">PIN-Authentifizierung wird für Skype for Business Online in Verbindung mit LPE- und Partner-IP-Telefonen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2ca31-161">PIN authentication isn't supported for Skype for Business Online for LPE and Partner IP phones.</span></span> 
  
- <span data-ttu-id="2ca31-p112">**Verwendung eines PCs**: Wenn auf den PCs von Benutzern BToE-Software (Better Together over Ethernet) installiert und aktiviert ist, können sich die Benutzer über das Authentifizierungsfenster in ihrer Skype for Business-App für Windows bei ihrem Telefon anmelden. Weitere Informationen finden Sie unter[Schritt 7 (optional) - Wenn Sie Gerätekopplung und Better Together over Ethernet (BToE) verwenden](deploying-skype-for-business-online-phones.md#BK_BTOE).</span><span class="sxs-lookup"><span data-stu-id="2ca31-p112">**Using a PC** When Better Together over Ethernet (BToE) software is installed on user's PC and enabled, users can log in to their phones using the authentication window on their Windows Skype for Business App. See[Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) for other information.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2ca31-p113">Die Benutzer müssen den Benutzernamen und das Kennwort der Organisation eingeben, um sich bei dem Telefon anzumelden. Für den Benutzernamen müssen sie das UPN-Format verwenden (zum Beispiel  *amosm@contoso.com*  ).</span><span class="sxs-lookup"><span data-stu-id="2ca31-p113">Users are required to use their organization's user name and password to sign in to the phone. For example, they should use the UPN format like  *amosm@contoso.com*  for their user name.</span></span>
  
     ![Bereitstellen von Telefonen.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- <span data-ttu-id="2ca31-p114">**Verwendung einer Webanmeldung**: Dies ist eine neue Methode, bei der sich Onlinebenutzer mit einem standardmäßigen Webbrowser authentifizieren können. Den Benutzern werden Anweisungen bereitgestellt, denen sie folgen müssen, wenn sie einen Browser für die Anmeldung verwenden.</span><span class="sxs-lookup"><span data-stu-id="2ca31-p114">**Using a Web Sign-in**: This is a new way for Online users to authenticate using a standard web browser. Users will be provided with a set of instructions to follow when they use a browser to sign in.</span></span>
    
  - <span data-ttu-id="2ca31-169">Benutzer mit **Polycom VVX 5XX/6XX** -Telefonen sehen folgenden Bildschirm:</span><span class="sxs-lookup"><span data-stu-id="2ca31-169">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Bereitstellen von Telefonen.](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - <span data-ttu-id="2ca31-171">Benutzer mit **Yealink T48G/T46G** -Telefonen sehen folgenden Bildschirm:</span><span class="sxs-lookup"><span data-stu-id="2ca31-171">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Yealink-Telefon-Login.](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    <span data-ttu-id="2ca31-p115">Der generierte Code läuft nach 15 Minuten ab. Wenn er abgelaufen ist, müssen die Benutzer je nach Telefon auf **Wiederholen** oder **OK** klicken, um einen neuen Code zu generieren.</span><span class="sxs-lookup"><span data-stu-id="2ca31-p115">The code that is generated will expire in 15 minutes. When it expires, the user will have to click **Retry** or **OK** to generate a new code, depending on the phone.</span></span>
    
  - <span data-ttu-id="2ca31-175">Benutzer mit **Polycom VVX 5XX/6XX** -Telefonen sehen folgenden Bildschirm:</span><span class="sxs-lookup"><span data-stu-id="2ca31-175">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Der PIN-Code ist abgelaufen.](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - <span data-ttu-id="2ca31-177">Benutzer mit **Yealink T48G/T46G** -Telefonen sehen folgenden Bildschirm:</span><span class="sxs-lookup"><span data-stu-id="2ca31-177">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Yealink-Telefon-Login.](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    <span data-ttu-id="2ca31-179">Navigieren Sie in einem Browser zu der auf dem Telefon angezeigten Adresse, und geben Sie Ihren Skype for Business-Benutzernamen ein.</span><span class="sxs-lookup"><span data-stu-id="2ca31-179">Using a browser, navigate to the address displayed on the phone and enter your Skype for Business username.</span></span>
    
     ![Bereitstellen von Telefonen.](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    <span data-ttu-id="2ca31-181">Geben Sie den auf dem Telefon angezeigten Code ein.</span><span class="sxs-lookup"><span data-stu-id="2ca31-181">Enter the code shown on the phone.</span></span>
    
     ![Bereitstellen von Telefonen.](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    <span data-ttu-id="2ca31-183">Vergewissern Sie sich, dass auf der Website „ **Skype for Business-zertifiziertes Telefon** von [Name des Telefonherstellers]" angezeigt wird, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="2ca31-183">Verify that the site shows "[Phone Manufacturer name] **Skype for Business Certified Phone**," and click **Continue**.</span></span>
    
     ![Bereitstellen von Telefonen.](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    <span data-ttu-id="2ca31-185">Klicken Sie auf die Anmeldeinformationen des Benutzers oder auf **Anderes Konto verwenden**:</span><span class="sxs-lookup"><span data-stu-id="2ca31-185">Click the user's credentials or click **Use another account**:</span></span>
    
     ![Bereitstellen von Telefonen.](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    <span data-ttu-id="2ca31-187">Wenn die folgende Seite angezeigt wird, können Sie den Browser gefahrlos schließen.</span><span class="sxs-lookup"><span data-stu-id="2ca31-187">When the following page is displayed, it is safe to close the browser.</span></span>
    
     ![Bereitstellen von Telefonen.](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > <span data-ttu-id="2ca31-189">LPE-Telefone für Skype for Business Online unterstützen nur die Anmeldung über USB-Tethering.</span><span class="sxs-lookup"><span data-stu-id="2ca31-189">LPE phones for Skype for Business Online support sign-in through USB tethering only.</span></span> 
  
- <span data-ttu-id="2ca31-190">**Unterstützte Bereitstellungen**: Die folgende Tabelle zeigt die unterstützten Authentifizierungstypen für die zurzeit unterstützten Bereitstellungsmodelle, beispielsweise Exchange-Integration, moderne Authentifizierung mit mehrstufiger Authentifizierung (Multi-factor Authentication, MFA) sowie Skype for Business Online und Skype for Business als lokale Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="2ca31-190">**Supported deployments** The table below shows the supported authentication types for the currently supported deployment models including Exchange Integration, Modern authentication with Multi-factor Authentication (MFA), and Skype for Business Online and on-premises.</span></span>
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2ca31-191">**Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="2ca31-191">**Skype for Business**</span></span> <br/> |<span data-ttu-id="2ca31-192">**Exchange**</span><span class="sxs-lookup"><span data-stu-id="2ca31-192">**Exchange**</span></span> <br/> |<span data-ttu-id="2ca31-193">**Methode für die Anmeldung beim Telefon**</span><span class="sxs-lookup"><span data-stu-id="2ca31-193">**Phone Sign-In method**</span></span> <br/> |<span data-ttu-id="2ca31-194">**Skype for Business-Zugriff**</span><span class="sxs-lookup"><span data-stu-id="2ca31-194">**Skype for Business access**</span></span> <br/> |<span data-ttu-id="2ca31-195">**Exchange-Zugriff mit moderner Authentifizierung und deaktivierter MFA**</span><span class="sxs-lookup"><span data-stu-id="2ca31-195">**Exchange Access with Modern Auth and MFA disabled**</span></span> <br/> |<span data-ttu-id="2ca31-196">**Exchange-Zugriff mit moderner Authentifizierung und aktivierter MFA**</span><span class="sxs-lookup"><span data-stu-id="2ca31-196">**Exchange Access with Modern Auth and MFA enabled**</span></span> <br/> |
|<span data-ttu-id="2ca31-197">Online</span><span class="sxs-lookup"><span data-stu-id="2ca31-197">Online</span></span>  <br/> |<span data-ttu-id="2ca31-198">Online</span><span class="sxs-lookup"><span data-stu-id="2ca31-198">Online</span></span>  <br/> |<span data-ttu-id="2ca31-199">Webanmeldung</span><span class="sxs-lookup"><span data-stu-id="2ca31-199">Web Sign-in</span></span>  <br/> |<span data-ttu-id="2ca31-200">Ja</span><span class="sxs-lookup"><span data-stu-id="2ca31-200">Yes</span></span>  <br/> |<span data-ttu-id="2ca31-201">Ja</span><span class="sxs-lookup"><span data-stu-id="2ca31-201">Yes</span></span>  <br/> |<span data-ttu-id="2ca31-202">Ja</span><span class="sxs-lookup"><span data-stu-id="2ca31-202">Yes</span></span>  <br/> |
|<span data-ttu-id="2ca31-203">Online</span><span class="sxs-lookup"><span data-stu-id="2ca31-203">Online</span></span>  <br/> |<span data-ttu-id="2ca31-204">Online</span><span class="sxs-lookup"><span data-stu-id="2ca31-204">Online</span></span>  <br/> |<span data-ttu-id="2ca31-205">Benutzername/Kennwort</span><span class="sxs-lookup"><span data-stu-id="2ca31-205">Username/Password</span></span>  <br/> |<span data-ttu-id="2ca31-206">Ja</span><span class="sxs-lookup"><span data-stu-id="2ca31-206">Yes</span></span>  <br/> |<span data-ttu-id="2ca31-207">Ja</span><span class="sxs-lookup"><span data-stu-id="2ca31-207">Yes</span></span>  <br/> |<span data-ttu-id="2ca31-208">Nein</span><span class="sxs-lookup"><span data-stu-id="2ca31-208">No</span></span>  <br/> |
|<span data-ttu-id="2ca31-209">Online</span><span class="sxs-lookup"><span data-stu-id="2ca31-209">Online</span></span>  <br/> |<span data-ttu-id="2ca31-210">Lokal</span><span class="sxs-lookup"><span data-stu-id="2ca31-210">On-premises</span></span>  <br/> |<span data-ttu-id="2ca31-211">Webanmeldung</span><span class="sxs-lookup"><span data-stu-id="2ca31-211">Web Sign-in</span></span>  <br/> |<span data-ttu-id="2ca31-212">Ja</span><span class="sxs-lookup"><span data-stu-id="2ca31-212">Yes</span></span>  <br/> |<span data-ttu-id="2ca31-213">Nein</span><span class="sxs-lookup"><span data-stu-id="2ca31-213">No</span></span>  <br/> |<span data-ttu-id="2ca31-214">Nein</span><span class="sxs-lookup"><span data-stu-id="2ca31-214">No</span></span>  <br/> |
|<span data-ttu-id="2ca31-215">Online</span><span class="sxs-lookup"><span data-stu-id="2ca31-215">Online</span></span>  <br/> |<span data-ttu-id="2ca31-216">Lokal</span><span class="sxs-lookup"><span data-stu-id="2ca31-216">On-Premises</span></span>  <br/> |<span data-ttu-id="2ca31-217">Benutzername/Kennwort</span><span class="sxs-lookup"><span data-stu-id="2ca31-217">Username/Password</span></span>  <br/> |<span data-ttu-id="2ca31-218">Ja</span><span class="sxs-lookup"><span data-stu-id="2ca31-218">Yes</span></span>  <br/> |<span data-ttu-id="2ca31-219">Ja</span><span class="sxs-lookup"><span data-stu-id="2ca31-219">Yes</span></span>  <br/> |<span data-ttu-id="2ca31-220">Nein</span><span class="sxs-lookup"><span data-stu-id="2ca31-220">No</span></span>  <br/> |
|<span data-ttu-id="2ca31-221">Lokal</span><span class="sxs-lookup"><span data-stu-id="2ca31-221">On-premises</span></span>  <br/> |<span data-ttu-id="2ca31-222">Online/lokal</span><span class="sxs-lookup"><span data-stu-id="2ca31-222">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="2ca31-223">PIN-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="2ca31-223">PIN Authentication</span></span>  <br/> |<span data-ttu-id="2ca31-224">Ja</span><span class="sxs-lookup"><span data-stu-id="2ca31-224">Yes</span></span>  <br/> |<span data-ttu-id="2ca31-225">Nein</span><span class="sxs-lookup"><span data-stu-id="2ca31-225">No</span></span>  <br/> |<span data-ttu-id="2ca31-226">Nein</span><span class="sxs-lookup"><span data-stu-id="2ca31-226">No</span></span>  <br/> |
|<span data-ttu-id="2ca31-227">Lokal</span><span class="sxs-lookup"><span data-stu-id="2ca31-227">On-premises</span></span>  <br/> |<span data-ttu-id="2ca31-228">Online/lokal</span><span class="sxs-lookup"><span data-stu-id="2ca31-228">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="2ca31-229">Benutzername/Kennwort</span><span class="sxs-lookup"><span data-stu-id="2ca31-229">Username/Password</span></span>  <br/> |<span data-ttu-id="2ca31-230">Ja</span><span class="sxs-lookup"><span data-stu-id="2ca31-230">Yes</span></span>  <br/> |<span data-ttu-id="2ca31-231">Ja</span><span class="sxs-lookup"><span data-stu-id="2ca31-231">Yes</span></span>  <br/> |<span data-ttu-id="2ca31-232">n/v</span><span class="sxs-lookup"><span data-stu-id="2ca31-232">N/A</span></span>  <br/> |
|<span data-ttu-id="2ca31-233">Lokal</span><span class="sxs-lookup"><span data-stu-id="2ca31-233">On-premises</span></span>  <br/> |<span data-ttu-id="2ca31-234">Online/lokal</span><span class="sxs-lookup"><span data-stu-id="2ca31-234">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="2ca31-235">Anmelden über PC (BToE)</span><span class="sxs-lookup"><span data-stu-id="2ca31-235">Sign-in via PC (BTOE)</span></span>  <br/> |<span data-ttu-id="2ca31-236">Ja</span><span class="sxs-lookup"><span data-stu-id="2ca31-236">Yes</span></span>  <br/> |<span data-ttu-id="2ca31-237">Ja</span><span class="sxs-lookup"><span data-stu-id="2ca31-237">Yes</span></span>  <br/> |<span data-ttu-id="2ca31-238">n/v</span><span class="sxs-lookup"><span data-stu-id="2ca31-238">N/A</span></span>  <br/> |
   
- <span data-ttu-id="2ca31-p116">**Telefonfunktionen**: Die Funktionen können sich je nach IP-Telefonpartner geringfügig unterscheiden. Eine Liste sämtlicher Funktionen und weitere Informationen zu den Funktionen der einzelnen Telefonhersteller finden Sie unter[Kauf von Telefonen für Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="2ca31-p116">**Phone features** The feature set may vary slightly based on the IP phone partner. For the complete feature set and for more information on the features for each phone manufacturer, see[Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="2ca31-p117">Die **Telefonsperre** ist eine kürzlich eingeführte Funktion von Skype for Business-zertifizierten Telefonen, mit der Telefone gesichert werden können. Wenn die Funktion aktiviert ist, werden die Benutzer aufgefordert, nach der erfolgreichen Authentifizierung eine PIN zu erstellen. Nach der Erstellung der PIN werden die Telefone gesperrt, wenn das von Ihnen definierte Leerlauftimeout abgelaufen ist, Benutzer ihr Telefon manuell sperren oder ihre Telefonsperre über die Telefonkopplung mit ihrem PC synchronisieren. Wenn die PIN für die Telefonsperre mehrmals falsch eingegeben wird, wird der Benutzer entweder abgemeldet oder das Telefon muss mit einem Administratorcode entsperrt werden. Dies ist jedoch je nach Telefonpartner unterschiedlich. Die PIN des Benutzers muss aus 6 bis 15 Ziffern bestehen.</span><span class="sxs-lookup"><span data-stu-id="2ca31-p117">**Phone-Lock** is a recently introduced feature in Skype for Business certified phones that is used to secure a phone. If enabled, users will be asked to create a PIN upon successful authentication. Once created, phones will lock when the idle-timeout that you define expires, a user manually locks their phone, or they sync their phone-lock with their PC lock using Phone Pairing. If the phone-lock PIN is entered wrong several times, the phone will either sign the user out or require an administrator's code to unlock the phone, but this will vary depending on the phone partner. The user's PIN should be between 6 and 15 digits.</span></span>
    
    <span data-ttu-id="2ca31-p118">Sie können die standardmäßig aktivierte Telefonsperre für Ihre Organisation deaktivieren, das Leerlauftimeout ändern und mithilfe von In-Band-Einstellungen auswählen, ob Benutzer trotz der Sperre Telefonanrufe tätigen können. Weitere Details zu diesen Einstellungen finden Sie unter [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).</span><span class="sxs-lookup"><span data-stu-id="2ca31-p118">You can disable Phone-Lock for your organization (which is enabled by default), change the idle-timeout, and choose whether users can make phone calls while they are locked or not using inband-settings. See [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) for more details on those settings.</span></span>
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a><span data-ttu-id="2ca31-248">Schritt 7 (optional) - Wenn Sie Gerätekopplung und Better Together over Ethernet (BToE) verwenden</span><span class="sxs-lookup"><span data-stu-id="2ca31-248">Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)</span></span>
<span data-ttu-id="2ca31-249"><a name="BK_BTOE"> </a></span><span class="sxs-lookup"><span data-stu-id="2ca31-249"><a name="BK_BTOE"> </a></span></span>

<span data-ttu-id="2ca31-p119">BToE ist ein Telefonkopplungsmechanismus für Partner-IP-Telefone, bei dem die Telefone der Benutzer mit ihrer Skype for Business-App für Windows gekoppelt werden. BToE bietet den Benutzern folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="2ca31-p119">BToE is a phone paining mechanism for Partner IP phones that pairs a user's phone with their Windows Skype for Business app. BToE enables users to:</span></span>
  
- <span data-ttu-id="2ca31-252">Anmelden bei ihrem IP-Telefon über die Skype for Business-Desktop-App (auf einem PC)</span><span class="sxs-lookup"><span data-stu-id="2ca31-252">Sign in to their IP phone using their Skype for Business desktop app (using a PC)</span></span>
    
- <span data-ttu-id="2ca31-253">Synchronisieren der Telefonsperre mit der PC-Sperre</span><span class="sxs-lookup"><span data-stu-id="2ca31-253">Synchronize Phone-Lock with PC lock</span></span>
    
- <span data-ttu-id="2ca31-254">Anruf per Mausklick</span><span class="sxs-lookup"><span data-stu-id="2ca31-254">Click to call</span></span>
    
<span data-ttu-id="2ca31-p120">BToE kann für den Betrieb in zwei Modi konfiguriert werden:  *Automatisch*  (Standard) und *Manuell*  . Außerdem kann es mit In-Band-Einstellungen von Skype for Business für Benutzer aktiviert (Standard) oder deaktiviert werden. Im Betrieb im Modus *Manuell*  müssen die Benutzer einen zusätzlichen Schritt ausführen, um ihr Telefon mit der Windows-App zu koppeln.</span><span class="sxs-lookup"><span data-stu-id="2ca31-p120">BToE can be configured to operate in two modes:  *Auto*  (default) and *Manual*  . It can also be enabled (default)/disabled for users using Skype for Business in-band settings. When operating in *Manual*  mode, users will have to take an additional step to pair their phone with their Windows app.</span></span>
  
 <span data-ttu-id="2ca31-258">**So stellen Sie BToE für Benutzer bereit**</span><span class="sxs-lookup"><span data-stu-id="2ca31-258">**To deploy BToE to users**</span></span>
  
1. <span data-ttu-id="2ca31-259">Verbinden Sie den PC über den PC-Anschluss mit dem Telefon.</span><span class="sxs-lookup"><span data-stu-id="2ca31-259">Connect their PC to their phone using the PC port.</span></span>
    
     ![Bereitstellen von Telefonen.](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. <span data-ttu-id="2ca31-p121">Laden Sie über die folgenden Links die neueste BToE-Software von der Website des entsprechenden Herstellers herunter. Sie können die Benutzerfreundlichkeit erhöhen, indem Sie die BToE-Software mit einer Administratorverteilungslösung wie System Center Configuration Manager (SCCM) verteilen und installieren. Hilfe zur Verwendung von SCCM finden Sie unter [Pakete und Programme in System Center Configuration Manager](https://docs.microsoft.com/en-us/sccm/apps/deploy-use/packages-and-programs).</span><span class="sxs-lookup"><span data-stu-id="2ca31-p121">Download and install the latest BToE software from the manufacturer website from the links below. For a better user experience, you can distribute and install the BToE software using an admin distribution solution such as System Center Configuration Manager (SCCM). For help using SCCM, See [Packages and programs in System Center Configuration Manager](https://docs.microsoft.com/en-us/sccm/apps/deploy-use/packages-and-programs).</span></span>
    
  - [<span data-ttu-id="2ca31-264">Polycom-Downloadwebsite für BToE-Software</span><span class="sxs-lookup"><span data-stu-id="2ca31-264">Polycom BToE Software Download site</span></span>](http://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
  - [<span data-ttu-id="2ca31-265">Yealink-Downloadwebsite für BToE-Software</span><span class="sxs-lookup"><span data-stu-id="2ca31-265">Yealink BToE Software Download</span></span>](http://www.yealink.com/products_list_10.html)
    
  - [<span data-ttu-id="2ca31-266">AudioCodes-Downloadwebsite für BToE-Software</span><span class="sxs-lookup"><span data-stu-id="2ca31-266">AudioCodes BToE Software Downloads</span></span>](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. <span data-ttu-id="2ca31-p122">Die Servereinstellung für BToE ist standardmäßig auf **Aktiviert** und **Automodus** festgelegt. Wie Sie diese Einstellungen ändern, erfahren Sie unter[Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).</span><span class="sxs-lookup"><span data-stu-id="2ca31-p122">The server setting for BToE is set to **Enabled** and **Auto mode** by default. To change those settings, see[Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).</span></span>
    
> [!NOTE]
> <span data-ttu-id="2ca31-269">BToE wird zurzeit auf Mac- und VDI-Plattformen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2ca31-269">BToE isn't currently supported on Mac and VDI platforms.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="2ca31-270">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="2ca31-270">Related topics</span></span>
[<span data-ttu-id="2ca31-271">Anfordern von Servicenummern für Skype for Business und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2ca31-271">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](../../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[<span data-ttu-id="2ca31-272">Das bekommen Sie mit Telefonsystem in Office 365</span><span class="sxs-lookup"><span data-stu-id="2ca31-272">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="2ca31-273">Verfügbarkeit von Land und Region für Audiokonferenz und Anrufpläne</span><span class="sxs-lookup"><span data-stu-id="2ca31-273">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
