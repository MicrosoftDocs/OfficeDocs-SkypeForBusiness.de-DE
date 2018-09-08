---
title: Aktivieren Sie die Benutzer für Enterprise Voice lokal
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: Für einen Benutzer in Office 365 (Cloud, PBX) Telefonsystem verwenden müssen Sie zuerst für Enterprise-VoIP zu aktivieren und weisen Sie ihnen eine Telefonnummer ein. Dieser Schritt wird mithilfe der lokalen bereitstellungs während der Benutzer noch in der lokalen Bereitstellung verwaltet wird.
ms.openlocfilehash: 8d00120b0b0fd74baed1ceb003a46cfc2468d502
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883376"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="02576-104">Aktivieren Sie die Benutzer für Enterprise Voice lokal</span><span class="sxs-lookup"><span data-stu-id="02576-104">Enable the users for Enterprise Voice on premises</span></span>
 
<span data-ttu-id="02576-105">Für einen Benutzer in Office 365 (Cloud, PBX) Telefonsystem verwenden müssen Sie zuerst für Enterprise-VoIP zu aktivieren und weisen Sie ihnen eine Telefonnummer ein.</span><span class="sxs-lookup"><span data-stu-id="02576-105">For a user to use Phone System in Office 365 (Cloud PBX), you must first enable them for Enterprise Voice and assign them a phone number.</span></span> <span data-ttu-id="02576-106">Dieser Schritt wird mithilfe der lokalen bereitstellungs während der Benutzer noch in der lokalen Bereitstellung verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="02576-106">You do this using your on-premises deployment while the user is still homed in the on-premises deployment.</span></span>
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a><span data-ttu-id="02576-107">Aktivieren von Benutzern für Enterprise-VoIP lokal und Zuweisen einer Telefonnummer</span><span class="sxs-lookup"><span data-stu-id="02576-107">To enable a user for Enterprise Voice on premises and assign a phone number</span></span>

1. <span data-ttu-id="02576-108">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="02576-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="02576-109">Benutzen Sie das Startmenü oder die Verknüpfung auf dem Desktop, um die Systemsteuerung von Skype for Business Server zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="02576-109">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    <span data-ttu-id="02576-110">Alternativ können Sie ein Browserfenster öffnen und dort die Admin-URL eingeben, um zur Systemsteuerung von Skype for Business Server zu gelangen.</span><span class="sxs-lookup"><span data-stu-id="02576-110">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="02576-111">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="02576-111">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="02576-112">Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das aktiviert werden soll und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="02576-112">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="02576-113">Klicken Sie in der Tabelle auf die Skype für Business Online Benutzerkonto, das Sie für Enterprise-VoIP aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="02576-113">In the table, click the Skype for Business Online user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="02576-114">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="02576-114">On the **Edit** menu, click **Show Details**.</span></span>
    
7. <span data-ttu-id="02576-115">Klicken Sie unter **Telefonie** auf **Enterprise-VoIP**.</span><span class="sxs-lookup"><span data-stu-id="02576-115">Under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="02576-p103">Klicken Sie auf **Anschluss-URI** und geben Sie eine eindeutige, normalisierte Telefonnummer ein (z. B. Tel:+14255550200). Klicken Sie dann auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="02576-p103">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200). Then click **Commit**.</span></span>
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="02576-118">Besondere Aspekte beim Aktivieren von Benutzern für Enterprise-VoIP lokal</span><span class="sxs-lookup"><span data-stu-id="02576-118">Special considerations when enabling users for Enterprise Voice on premises</span></span>

<span data-ttu-id="02576-119">In einigen Fällen kann es vorkommen, dass Sie die Vorgehensweise hinsichtlich der Aktivierung von Benutzern für Enterprise-VoIP ändern müssen, damit Benutzer erfolgreich Anrufe tätigen und empfangen können.</span><span class="sxs-lookup"><span data-stu-id="02576-119">In some cases, you may need to modify the way you enable users for Enterprise Voice to make sure that they can successfully make and receive calls.</span></span> <span data-ttu-id="02576-120">Wenn Sie Benutzer in Ihrer Bereitstellung vorhanden, die die folgenden Kriterien erfüllen sind, führen Sie die Schritte zum Aktivieren des Benutzers für Enterprise-VoIP eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="02576-120">If you have users in your deployment that meet the following conditions, perform the steps included to enable the user for Enterprise Voice.</span></span>
  
- <span data-ttu-id="02576-121">Wenn ein Benutzer, in Ihrer lokalen erstellt wird AD und ohne für Skype für Unternehmen oder für Enterprise Voice aktiviert mit Skype für Online Business synchronisiert und verfügen nicht über einen "lineuri" festgelegt ist, führen Sie die folgenden Cmdlets für jeden betroffenen Benutzer, ersetzen die Werte in < C0 > <b1></b1> durch tatsächliche Werte für Ihre Umgebung:</span><span class="sxs-lookup"><span data-stu-id="02576-121">If a user is created in your on-premises AD and then synchronized with Skype for Business Online without being enabled for Skype for Business or for Enterprise Voice and do not have a LineURI set, run the following cmdlets for each affected user, replacing the values in \< \> with actual values for your environment:</span></span>
    
  ```
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="02576-122">Wenn ein Benutzer bereits für Skype für Unternehmen lokal, aktiviert ist wurde jedoch nicht für Enterprise Voice aktiviert oder einen "lineuri" zugewiesen, bevor in Skype für Business Online verschoben, führen Sie für jeden Benutzer das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="02576-122">If a user is already enabled for Skype for Business on premises, but was not enabled for Enterprise Voice or assigned a LineURI before being moved to Skype for Business Online, run the following cmdlet for each user:</span></span>
    
  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="02576-123">Wenn ein Benutzer bereits in Skype für Unternehmen lokal aktiviert aber nicht für Enterprise-VoIP aktiviert, auch wenn bereits ein Anschluss-URI zugewiesen ist, führen Sie für jeden betroffenen Benutzer das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="02576-123">If a user is already enabled in Skype for Business on premises but not enabled for Enterprise Voice, even if already assigned a LineURI, run the following cmdlet for each affected user:</span></span>
    
  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


