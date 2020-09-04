---
title: Aktivieren der Benutzer für Enterprise-VoIP lokal
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: Damit ein Benutzer das Telefon System (Cloud PBX) verwenden kann, müssen Sie ihn zunächst für Enterprise-VoIP aktivieren und ihm eine Telefonnummer zuweisen. Verwenden Sie dazu Ihre lokale Bereitstellung, während der Benutzer noch in der lokalen Bereitstellung verwaltet wird.
ms.openlocfilehash: 7fc629114900cb9f4d825bd8fdc8e946e6c63880
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359191"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="8f77e-104">Aktivieren der Benutzer für Enterprise-VoIP lokal</span><span class="sxs-lookup"><span data-stu-id="8f77e-104">Enable the users for Enterprise Voice on premises</span></span>
 
<span data-ttu-id="8f77e-105">Damit ein Benutzer das Telefon System (Cloud PBX) verwenden kann, müssen Sie ihn zunächst für Enterprise-VoIP aktivieren und ihm eine Telefonnummer zuweisen.</span><span class="sxs-lookup"><span data-stu-id="8f77e-105">For a user to use Phone System (Cloud PBX), you must first enable them for Enterprise Voice and assign them a phone number.</span></span> <span data-ttu-id="8f77e-106">Verwenden Sie dazu Ihre lokale Bereitstellung, während der Benutzer noch in der lokalen Bereitstellung verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="8f77e-106">You do this using your on-premises deployment while the user is still homed in the on-premises deployment.</span></span>

> [!Important]
> <span data-ttu-id="8f77e-107">Skype for Business Online werden am 31. Juli 2021 zurückgezogen, nach dem der Zugriff auf den Dienst nicht mehr möglich ist.</span><span class="sxs-lookup"><span data-stu-id="8f77e-107">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="8f77e-108">Darüber hinaus wird die PSTN-Konnektivität zwischen Ihrer lokalen Umgebung unabhängig davon, ob über Skype for Business Server oder Cloud Connector Edition und Skype for Business Online nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8f77e-108">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="8f77e-109">Hier erfahren Sie, wie Sie Ihr lokales Telefonie-Netzwerk mithilfe des [direkten Routings](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)mit Microsoft Teams verbinden.</span><span class="sxs-lookup"><span data-stu-id="8f77e-109">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a><span data-ttu-id="8f77e-110">So aktivieren Sie einen Benutzer für Enterprise-VoIP lokal und weisen eine Telefonnummer zu</span><span class="sxs-lookup"><span data-stu-id="8f77e-110">To enable a user for Enterprise Voice on premises and assign a phone number</span></span>

1. <span data-ttu-id="8f77e-111">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="8f77e-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="8f77e-112">Verwenden Sie das Startmenü oder die Verknüpfung auf dem Desktop, um die Skype for Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="8f77e-112">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    <span data-ttu-id="8f77e-113">Sie können auch ein Browserfenster öffnen und die Administrator-URL eingeben, um die Skype for Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="8f77e-113">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="8f77e-114">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="8f77e-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="8f77e-115">Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das aktiviert werden soll, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="8f77e-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="8f77e-116">Klicken Sie in der Tabelle auf das Skype for Business Online Benutzerkonto, das Sie für Enterprise-VoIP aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="8f77e-116">In the table, click the Skype for Business Online user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="8f77e-117">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="8f77e-117">On the **Edit** menu, click **Show Details**.</span></span>
    
7. <span data-ttu-id="8f77e-118">Klicken Sie unter **Telefonie**auf **Enterprise-VoIP**.</span><span class="sxs-lookup"><span data-stu-id="8f77e-118">Under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="8f77e-119">Klicken Sie auf **Leitungs-URI**, und geben Sie eine eindeutige, normalisierte Telefonnummer ein (beispielsweise Tel: + 14255550200).</span><span class="sxs-lookup"><span data-stu-id="8f77e-119">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200).</span></span> <span data-ttu-id="8f77e-120">Klicken Sie dann auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="8f77e-120">Then click **Commit**.</span></span>
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="8f77e-121">Besondere Überlegungen beim Aktivieren von Benutzern für Enterprise-VoIP vor Ort</span><span class="sxs-lookup"><span data-stu-id="8f77e-121">Special considerations when enabling users for Enterprise Voice on premises</span></span>

<span data-ttu-id="8f77e-122">In einigen Fällen müssen Sie möglicherweise die Art und Weise ändern, wie Sie Benutzer für Enterprise-VoIP aktivieren, um sicherzustellen, dass Sie Anrufe erfolgreich tätigen und empfangen können.</span><span class="sxs-lookup"><span data-stu-id="8f77e-122">In some cases, you may need to modify the way you enable users for Enterprise Voice to make sure that they can successfully make and receive calls.</span></span> <span data-ttu-id="8f77e-123">Wenn Sie über Benutzer in Ihrer Bereitstellung verfügen, die die folgenden Bedingungen erfüllen, führen Sie die Schritte aus, die zum Aktivieren des Benutzers für Enterprise-VoIP erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="8f77e-123">If you have users in your deployment that meet the following conditions, perform the steps included to enable the user for Enterprise Voice.</span></span>
  
- <span data-ttu-id="8f77e-124">Wenn ein Benutzer in Ihrer lokalen AD erstellt und dann mit Skype for Business Online synchronisiert wird, ohne für Skype for Business oder Enterprise-VoIP aktiviert zu sein und kein LineURI festgelegt wurde, führen Sie die folgenden Cmdlets für jeden betroffenen Benutzer aus, und ersetzen Sie die Werte in \< \> durch tatsächliche Werte für Ihre Umgebung:</span><span class="sxs-lookup"><span data-stu-id="8f77e-124">If a user is created in your on-premises AD and then synchronized with Skype for Business Online without being enabled for Skype for Business or for Enterprise Voice and do not have a LineURI set, run the following cmdlets for each affected user, replacing the values in \< \> with actual values for your environment:</span></span>
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="8f77e-125">Wenn ein Benutzer bereits für Skype for Business lokal aktiviert ist, jedoch nicht für Enterprise-VoIP aktiviert wurde oder ein LineURI zugewiesen wurde, bevor er in Skype for Business Online verschoben wurde, führen Sie für jeden Benutzer das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="8f77e-125">If a user is already enabled for Skype for Business on premises, but was not enabled for Enterprise Voice or assigned a LineURI before being moved to Skype for Business Online, run the following cmdlet for each user:</span></span>
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="8f77e-126">Wenn ein Benutzer bereits in Skype for Business lokal aktiviert, aber für Enterprise-VoIP nicht aktiviert ist, führen Sie das folgende Cmdlet für jeden betroffenen Benutzer aus, wenn bereits ein LineURI zugewiesen ist:</span><span class="sxs-lookup"><span data-stu-id="8f77e-126">If a user is already enabled in Skype for Business on premises but not enabled for Enterprise Voice, even if already assigned a LineURI, run the following cmdlet for each affected user:</span></span>
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


