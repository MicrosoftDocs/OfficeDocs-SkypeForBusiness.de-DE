---
title: Autorisieren des Gastzugriffs in Microsoft Teams
author: lolaj
ms.author: sbhatta
manager: serdars
ms.date: 11/10/17
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: sbhatta
search.appverid: MET150
description: Verwalten Sie die Features und Funktionen für den Gastzugriff in Microsoft Teams mit vier verschiedenen Autorisierungsebenen.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f5b0acd36c83f59b1883115a76d6295e1e9cb454
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "25012010"
---
<a name="authorize-guest-access-in-microsoft-teams"></a><span data-ttu-id="d8c00-103">Autorisieren des Gastzugriffs in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d8c00-103">Authorize guest access in Microsoft Teams</span></span>
===========================================

<span data-ttu-id="d8c00-104">Um die Anforderungen Ihrer Organisation zu erfüllen, können Sie die Features und Funktionen für den Gastzugriff in Microsoft Teams mit vier verschiedenen Autorisierungsebenen verwalten.</span><span class="sxs-lookup"><span data-stu-id="d8c00-104">To satisfy your organization’s requirements, you can manage Microsoft Teams guest access features and capabilities through four different levels of authorization.</span></span> <span data-ttu-id="d8c00-105">Alle Autorisierungsebenen gelten für Ihren Office 365-Mandanten.</span><span class="sxs-lookup"><span data-stu-id="d8c00-105">All the authorization levels apply to your Office 365 tenant.</span></span> <span data-ttu-id="d8c00-106">Die einzelnen Autorisierungsebenen steuern den Gastzugriff wie unten beschrieben:</span><span class="sxs-lookup"><span data-stu-id="d8c00-106">Each authorization level controls the guest experience as shown below:</span></span>
- <span data-ttu-id="d8c00-107">**Azure Active Directory**: Für den Gastzugriff in Microsoft Teams wird die Azure AD B2B-Plattform (Business-to-Business) genutzt.</span><span class="sxs-lookup"><span data-stu-id="d8c00-107">**Azure Active Directory**: Guest access in Microsoft Teams relies on the Azure AD business-to-business (B2B) platform.</span></span> <span data-ttu-id="d8c00-108">Steuert den Gastzugriff auf Verzeichnis-, Mandanten- und Anwendungsebene.</span><span class="sxs-lookup"><span data-stu-id="d8c00-108">Controls the guest experience at the directory, tenant, and application level.</span></span> 
- <span data-ttu-id="d8c00-109">**Microsoft Teams**: Steuert nur Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d8c00-109">**Microsoft Teams**: Controls Microsoft Teams only.</span></span> 
- <span data-ttu-id="d8c00-110">**Office 365-Gruppen**: Steuert den Gastzugriff in Office 365-Gruppen und in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d8c00-110">**Office 365 Groups**: Controls the guest experience in Office 365 Groups and Microsoft Teams.</span></span>
- <span data-ttu-id="d8c00-111">**SharePoint Online und OneDrive for Business**: Steuert den Gastzugriff in SharePoint Online, OneDrive for Business, Office 365-Gruppen und Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d8c00-111">**SharePoint Online and OneDrive for Business**: Controls the guest experience in SharePoint Online, OneDrive for Business, Office 365 Groups, and Microsoft Teams.</span></span>

<span data-ttu-id="d8c00-112">Diese verschiedenen Autorisierungsebenen bieten Ihnen Flexibilität beim Einrichten des Gastzugriffs für Ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="d8c00-112">These different authorization levels provide you with flexibility in how you set up guest access for your organization.</span></span> <span data-ttu-id="d8c00-113">Wenn Sie zum Beispiel in Ihrer Microsoft Teams-Organisation keine Gastbenutzer zulassen möchten, deaktivieren Sie einfach den Gastzugriff in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d8c00-113">For example, if you don’t want to allow guest users in your Microsoft Teams organization, just turn off guest access in Microsoft Teams.</span></span> <span data-ttu-id="d8c00-114">Ein weiteres Beispiel: Sie können den Gastzugriff auf AAD-Ebene, Microsoft Teams-Ebene und Gruppenebene aktivieren, aber dann das Hinzufügen von Gastbenutzern zu ausgewählten Teams deaktivieren, die einem oder mehreren Kriterien (z. B. der Datenklassifizierung „Vertraulich“) entsprechen.</span><span class="sxs-lookup"><span data-stu-id="d8c00-114">Another example: You could enable guest access at the AAD, Teams, and Groups levels, but then disable guest users' addition on selected teams that match one or more criteria such as data classification equals confidential.</span></span> <span data-ttu-id="d8c00-115">Vielleicht verwenden Sie auch keine Office 365-Gruppen.</span><span class="sxs-lookup"><span data-stu-id="d8c00-115">And, perhaps you don’t use Office 365 Groups.</span></span> <span data-ttu-id="d8c00-116">Für SharePoint Online und OneDrive for Business gibt es eigene Einstellungen für den Gastzugriff, die nicht auf Office 365-Gruppen basieren.</span><span class="sxs-lookup"><span data-stu-id="d8c00-116">SharePoint Online and OneDrive for Business have their own guest access settings that don't rely on Office 365 Groups.</span></span> 

> [!NOTE]
> <span data-ttu-id="d8c00-117">Gäste unterliegen den [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347)- und [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019)-Dienstbeschränkungen.</span><span class="sxs-lookup"><span data-stu-id="d8c00-117">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span> 

  <span data-ttu-id="d8c00-118">Das folgende Diagramm zeigt, wie die Abhängigkeit der Gastzugriffsautorisierung zwischen Azure Active Directory, Microsoft Teams und Office 365 gewährt und integriert wird.</span><span class="sxs-lookup"><span data-stu-id="d8c00-118">The following diagram shows how guest access authorization dependency is granted and integrated between Azure Active Directory, Microsoft Teams, and Office 365.</span></span>


![Diagramm der Autorisierungsabhängigkeiten für den Gastzugriff](media/teams_dependencies_image1.png)


## <a name="azure-active-directory"></a><span data-ttu-id="d8c00-120">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="d8c00-120">Azure Active Directory</span></span>

<span data-ttu-id="d8c00-121">Mit Azure AD B2B-Zusammenarbeit ist das Senden von Einladungen an potenzielle Gastbenutzer nicht auf Mandantenadministratoren beschränkt.</span><span class="sxs-lookup"><span data-stu-id="d8c00-121">With Azure AD business-to-business (B2B) collaboration, sending invitations to potential guest users isn’t restricted to tenant admins.</span></span> <span data-ttu-id="d8c00-122">Sie können stattdessen Richtlinien verwenden, um das Senden von Einladungen an Benutzer zu delegieren, die aufgrund ihrer Rollen Einladungen senden können.</span><span class="sxs-lookup"><span data-stu-id="d8c00-122">Instead, you can use policies to delegate sending invitations to users whose roles allow them to send invitations.</span></span>

<span data-ttu-id="d8c00-123">Die Einstellungen für Einladungen gelten auf Mandantenebene und steuern den Gastzugriff auf Verzeichnis-, Mandanten- und Anwendungsebene.</span><span class="sxs-lookup"><span data-stu-id="d8c00-123">The settings for invitations apply at the tenant level and control the guest experience at the directory, tenant, and application level.</span></span> <span data-ttu-id="d8c00-124">Mindestens zur Unterstützung von Gäste müssen **Mitglieder einladen können** auf **Ja**festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="d8c00-124">At a minimum to support guests, **Members can invite** must be set to **Yes**.</span></span>


![Screenshot der Benutzereinstellungen im Azure Active Directory-Portal](media/teams_dependencies_image2.png)

<span data-ttu-id="d8c00-126">Azure AD umfasst die folgenden Einstellungen zum Konfigurieren von externer Benutzern:</span><span class="sxs-lookup"><span data-stu-id="d8c00-126">Azure AD includes the following settings to configure external users:</span></span>
- <span data-ttu-id="d8c00-127">**Benutzerberechtigungen Gast sind beschränkt**: **Ja** bedeutet, dass Gäste nicht über die Berechtigung für bestimmte Verzeichnisaufgaben verfügen, wie Aufzählen von Benutzern, Gruppen oder andere Directory Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="d8c00-127">**Guest user permissions are limited**: **Yes** means that guests don't have permission for certain directory tasks, such as enumerate users, groups, or other directory resources.</span></span> <span data-ttu-id="d8c00-128">Darüber hinaus können nicht Gäste Administratorrollen in Ihrem Verzeichnis zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="d8c00-128">In addition, guests can't be assigned to administrative roles in your directory.</span></span> <span data-ttu-id="d8c00-129">**Keine** Möglichkeit, die Gäste haben den gleichen Zugriff auf Directory-Daten, die in Ihrem Verzeichnis reguläre Benutzer haben.</span><span class="sxs-lookup"><span data-stu-id="d8c00-129">**No** means that guests have the same access to directory data that regular users have in your directory.</span></span>
- <span data-ttu-id="d8c00-130">**Administratoren und Benutzer in die Guest-Rolle eingeladenen können einladen**: **Ja** bedeutet, dass Administratoren und Benutzer in der Rolle "Gast eingeladenen" Gäste, die dem Mandanten einladen können.</span><span class="sxs-lookup"><span data-stu-id="d8c00-130">**Admins and users in the guest inviter role can invite**: **Yes** means that admins and users in the "Guest Inviter" role will be able to invite guests to the tenant.</span></span> <span data-ttu-id="d8c00-131">**No** bedeutet, dass Administratoren und Benutzer können keine Gäste, die dem Mandanten einladen.</span><span class="sxs-lookup"><span data-stu-id="d8c00-131">**No** means admins and users can't invite guests to the tenant.</span></span>
- <span data-ttu-id="d8c00-132">**Mitglieder können einladen**: **Ja** bedeutet, dass nicht-Administrator Mitglieder Ihres Verzeichnisses Gäste auf Ressourcen, die durch Ihre Azure AD, wie SharePoint-Websites oder Azure Ressourcen gesichert Zusammenarbeit einladen können.</span><span class="sxs-lookup"><span data-stu-id="d8c00-132">**Members can invite**: **Yes** means that non-admin members of your directory can invite guests to collaborate on resources secured by your Azure AD, such as SharePoint sites or Azure resources.</span></span> <span data-ttu-id="d8c00-133">**No** bedeutet, dass nur Administratoren einladen können, die in das Verzeichnis Gäste.</span><span class="sxs-lookup"><span data-stu-id="d8c00-133">**No** means that only admins can invite guests to your directory.</span></span>
- <span data-ttu-id="d8c00-134">**Gäste können einladen**: **Ja** bedeutet, dass Gäste in Ihrem Verzeichnis selbst anderen Gast auf Ressourcen, die durch Ihre Azure AD, wie SharePoint-Websites oder Azure Ressourcen gesichert Zusammenarbeit einladen können.</span><span class="sxs-lookup"><span data-stu-id="d8c00-134">**Guests can invite**: **Yes** means that guests in your directory can themselves invite other guest to collaborate on resources secured by your Azure AD, such as SharePoint sites or Azure resources.</span></span> <span data-ttu-id="d8c00-135">**Keine** Möglichkeit, die Gäste einladen nicht andere Gäste für die Zusammenarbeit mit Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="d8c00-135">**No** means that guests can't invite other guests to collaborate with your organization.</span></span>
 


> [!NOTE]
> <span data-ttu-id="d8c00-136">Sie können auch verwalten, welche Domänen in Ihrem Mandanten als Gäste eingeladen werden können.</span><span class="sxs-lookup"><span data-stu-id="d8c00-136">You can also manage which domains can be invited into your tenant as guests.</span></span> <span data-ttu-id="d8c00-137">Finden Sie unter [Zulassen/Blockieren Gast des Zugriffs auf Office 365-Gruppen](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-group-access-to-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="d8c00-137">See [Allow/Block guest access to Office 365 groups](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-group-access-to-office-365-groups).</span></span> 

## <a name="microsoft-teams"></a><span data-ttu-id="d8c00-138">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d8c00-138">Microsoft Teams</span></span>
<span data-ttu-id="d8c00-139">Sie können in Microsoft Teams steuern, ob der Gastzugriff für Ihre Organisation aktiviert oder deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="d8c00-139">In Microsoft Teams, you can control whether the guest experience is enabled or disabled for your organization.</span></span> <span data-ttu-id="d8c00-140">Die Einstellung ist standardmäßig deaktiviert und gilt auf Mandantenebene nur für Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d8c00-140">The setting is disabled by default and applies at the tenant level for Microsoft Teams only.</span></span>



<span data-ttu-id="d8c00-141">Sie können die Einstellungen für den Gastzugriff in Microsoft Teams über das Office 365 Admin Center verwalten.</span><span class="sxs-lookup"><span data-stu-id="d8c00-141">You can manage Microsoft Teams guest access settings from the Office 365 admin center.</span></span> <span data-ttu-id="d8c00-142">Weitere Informationen finden Sie unter [Aktivieren oder Deaktivieren des Gastzugriffs auf Microsoft Teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="d8c00-142">For more information, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span> 


## <a name="office-365-groups"></a><span data-ttu-id="d8c00-143">Office 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="d8c00-143">Office 365 Groups</span></span>

<span data-ttu-id="d8c00-144">Über Office 365-Gruppen können Sie das Hinzufügen von Gastbenutzern sowie den Gastzugriff auf alle Office 365-Gruppen und auf Microsoft Teams in Ihrer Organisation steuern.</span><span class="sxs-lookup"><span data-stu-id="d8c00-144">From Office 365 Groups, you can control adding guest users and guest access to all Office 365 groups and Microsoft Teams in your organization.</span></span>

1. <span data-ttu-id="d8c00-145">Melden Sie sich mit dem Konto Globaler Office 365-Administrator bei [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) an.</span><span class="sxs-lookup"><span data-stu-id="d8c00-145">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
  
2. <span data-ttu-id="d8c00-146">Wählen Sie im Navigationsmenü **Einstellungen** und dann **Dienste &amp; Add-Ins** aus.</span><span class="sxs-lookup"><span data-stu-id="d8c00-146">In the navigation menu, choose **Settings** and then select **Services &amp; add-ins**.</span></span>
    
  
3. <span data-ttu-id="d8c00-147">Wählen Sie **Office 365-Gruppen** aus.</span><span class="sxs-lookup"><span data-stu-id="d8c00-147">Select **Office 365 Groups**.</span></span>
    
     ![Office 365-Gruppen](media/e25a7920-254c-4da3-bc5f-a8c7f6b61423.png)
  

  

  
4. <span data-ttu-id="d8c00-149">Je nachdem, ob Sie den Zugriff für Team- oder Gruppenbesitzer außerhalb Ihres Unternehmens auf Office 365-Gruppen gewähren möchten, legen Sie die Umschaltfläche auf der Seite „Office 365-Gruppen“ auf **Ein** oder **Aus** fest.</span><span class="sxs-lookup"><span data-stu-id="d8c00-149">On the Office 365 Groups page, set the toggle to **On** or **Off**, depending if you want to let team and group owners outside your organization access Office 365 groups.</span></span> <span data-ttu-id="d8c00-150">Klicken oder tippen Sie neben **Hinzufügen von Personen außerhalb der Organisation zu Gruppen durch Gruppenbesitzer zulassen** auf die Umschaltfläche, um sie in **Ein** zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d8c00-150">Click or tap the toggle to **On** next to **Let group owners add people outside the organization to groups**.</span></span> <span data-ttu-id="d8c00-151">Wenn Sie diese Umschaltfläche in „Ein“ ändern, sehen Sie eine weitere Option. Mit dieser können Sie steuern, ob es Gruppen- und Teambesitzern möglich sein soll, Personen außerhalb der Organisation zu Office 365-Gruppen und Microsoft Teams hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="d8c00-151">If you turn this toggle to On, you'll see another option to control whether you want to let group and team owners add people outside your organization to Office 365 groups and Microsoft teams.</span></span> <span data-ttu-id="d8c00-152">Legen Sie diese Umschaltfläche auf „Ein“ fest, wenn Sie Gruppen- und Teambesitzern das Hinzufügen von Gastbenutzern ermöglichen möchten.</span><span class="sxs-lookup"><span data-stu-id="d8c00-152">Set this toggle to On if you want to let group and team owners add guest users.</span></span> <span data-ttu-id="d8c00-153">![Dieser Screenshot bildet den Office 365 Groups-Bereich mit den aktivierten Optionen für den Zugriff von Gruppenmitgliedern außerhalb der Organisation auf Gruppeninhalte sowie für das Hinzufügen von Personen außerhalb der Organisation zu Gruppen durch Gruppenbesitzer ab.](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)</span><span class="sxs-lookup"><span data-stu-id="d8c00-153">![Screenshot shows the Office 365 Groups panel with the options turned on to let group members outside the organization access group content and to let group owners add people outside the organization to groups.](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)</span></span>




<span data-ttu-id="d8c00-154">Die oben genannten Einstellungen gelten auf Mandantenebene und steuern den Gastzugriff in Office 365-Gruppen und in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d8c00-154">The above settings apply at the tenant level and control the guest experience in Office 365 Groups and Microsoft Teams.</span></span>


## <a name="sharepoint-online-and-onedrive-for-business"></a><span data-ttu-id="d8c00-155">SharePoint Online und OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="d8c00-155">SharePoint Online and OneDrive for Business</span></span>

<span data-ttu-id="d8c00-156">Teams nutzt SharePoint Online und OneDrive for Business zum Speichern von Dateien und Dokumenten für Kanäle und Chatunterhaltungen.</span><span class="sxs-lookup"><span data-stu-id="d8c00-156">Teams relies on SharePoint Online and OneDrive for Business to store files and documents for channels and chat conversations.</span></span>  
  
    
    
<span data-ttu-id="d8c00-157">Um alle Gastzugriffsfunktionen in Microsoft Teams zu aktivieren, müssen Office 365-Administratoren für die folgenden Einstellungen die Option **Ein** auswählen:</span><span class="sxs-lookup"><span data-stu-id="d8c00-157">To enable the full Teams guest access experience, Office 365 admins need to select **On** for the following settings:</span></span>
  
    
    

- <span data-ttu-id="d8c00-158">In SharePoint Online: **Freigabe nur für bereits im Verzeichnis enthaltenen externen Benutzern zulassen**</span><span class="sxs-lookup"><span data-stu-id="d8c00-158">In SharePoint Online: **Only allow sharing with external users already in the directory**</span></span>
    
    <span data-ttu-id="d8c00-159">Weitere Informationen finden Sie unter [Verwalten von externer Freigabe für Ihre SharePoint Online-Umgebung](https://docs.microsoft.com/sharepoint/external-sharing-overview).</span><span class="sxs-lookup"><span data-stu-id="d8c00-159">For more information, see [Manage external sharing for your SharePoint Online environment](https://docs.microsoft.com/sharepoint/external-sharing-overview).</span></span>
    
  
- <span data-ttu-id="d8c00-160">In Office 365-Gruppen: **Hinzufügen von Personen außerhalb der Organisation zu Gruppen durch Gruppenbesitzer zulassen**</span><span class="sxs-lookup"><span data-stu-id="d8c00-160">In Office 365 groups: **Let group owners add people outside the organization to groups**</span></span>
    
    <span data-ttu-id="d8c00-161">Weitere Informationen finden Sie unter [Steuern des Gastzugriffs auf Microsoft Teams](#controlguest).</span><span class="sxs-lookup"><span data-stu-id="d8c00-161">For more information, see [Control guest access to Microsoft Teams](#controlguest).</span></span>
  

<span data-ttu-id="d8c00-162">Die oben genannten Einstellungen gelten auf Mandantenebene und steuern den Gastzugriff in SharePoint Online, OneDrive for Business, Office 365-Gruppen und Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d8c00-162">The above settings apply at the tenant level and control the guest experience at SharePoint Online, OneDrive for Business, Office 365 Groups and Microsoft Teams.</span></span>


<span data-ttu-id="d8c00-163">Sie können SharePoint Online-Einstellungen für externe Benutzer für die mit Microsoft Teams verbundene Teamwebsite verwalten.</span><span class="sxs-lookup"><span data-stu-id="d8c00-163">You can manage SharePoint Online external user settings for the Teams connected team site.</span></span> <span data-ttu-id="d8c00-164">Weitere Einzelheiten finden Sie unter [Verwalten der Einstellungen Ihrer SharePoint-Teamwebsite](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).﻿</span><span class="sxs-lookup"><span data-stu-id="d8c00-164">For more details, see  [Manage your SharePoint team site settings](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).</span></span>
