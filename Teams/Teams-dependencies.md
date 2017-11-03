---
title: "Office 365-Abhängigkeiten für Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
description: "Microsoft Teams nutzt Office 365-Gruppen, SharePoint Online und OneDrive for Business."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: e04770535976f509a8ac16cf054ea5e6760b5231
ms.sourcegitcommit: f6c2673a2ccd951770296972234938e627bd49ad
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2017
---
<a name="office-365-dependencies-for-microsoft-teams"></a><span data-ttu-id="b3d7e-103">Office 365-Abhängigkeiten für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b3d7e-103">Office 365 licensing for Microsoft Teams</span></span>
===========================================

<span data-ttu-id="b3d7e-104">Microsoft Teams nutzt Office 365-Gruppen zum Speichern von Teammitgliedschaften und anderen Eigenschaften, wie zum Beispiel Einstellungen zur Klassifizierung von Teamdaten.</span><span class="sxs-lookup"><span data-stu-id="b3d7e-104">In addition, Microsoft Teams relies on Office 365 groups to store teams' memberships and other properties such as team data classification settings.</span></span> <span data-ttu-id="b3d7e-105">Office 365-Gruppen ist ein Dienst, der anwendungsübergreifende Mitgliedschaft für bestimmte freigegebene Teamressourcen (beispielsweise eine SharePoint-Website oder ein Power BI-Dashboard) bietet, damit das Team effektiv und sicher zusammenarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="b3d7e-105">Office 365 Groups is a service that provides cross-application membership for a set of shared team assets, like a SharePoint site or a Power BI dashboard, so that the team can collaborate effectively and securely.</span></span> 

<span data-ttu-id="b3d7e-106">Microsoft Teams nutzt außerdem SharePoint Online und OneDrive for Business zum Speichern von Dateien und Dokumenten für Kanäle und Chatunterhaltungen.</span><span class="sxs-lookup"><span data-stu-id="b3d7e-106">Teams relies on SharePoint Online and OneDrive for Business to store files and documents for channels and chat conversations.</span></span> <span data-ttu-id="b3d7e-107">Microsoft Teams nutzt darüber hinaus Office 365-Gruppen zum Speichern von Teammitgliedschaften und anderen Eigenschaften, wie zum Beispiel Einstellungen zur Klassifizierung von Teamdaten.</span><span class="sxs-lookup"><span data-stu-id="b3d7e-107">In addition, Teams relies on Office 365 groups to store teams' memberships and other properties such as team data classification settings.</span></span> <span data-ttu-id="b3d7e-108">Gäste unterliegen den [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347)- und [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019)-Dienstbeschränkungen.</span><span class="sxs-lookup"><span data-stu-id="b3d7e-108">Yes, guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>
  
    
    
<span data-ttu-id="b3d7e-109">Um alle Gastzugriffsfunktionen in Microsoft Teams zu aktivieren, müssen Office 365-Administratoren für die folgenden Einstellungen die Option **Ein** auswählen:</span><span class="sxs-lookup"><span data-stu-id="b3d7e-109">To enable the full Teams guest access experience, Office 365 admins need to select **On** for the following settings:</span></span>
  
    
    

- <span data-ttu-id="b3d7e-110">In SharePoint Online: **Freigabe nur für bereits im Verzeichnis enthaltenen externen Benutzern zulassen**</span><span class="sxs-lookup"><span data-stu-id="b3d7e-110">In SharePoint Online: **Only allow sharing with external users already in the directory**</span></span>
    
    <span data-ttu-id="b3d7e-111">Weitere Informationen finden Sie unter [Verwalten von externer Freigabe für Ihre SharePoint Online-Umgebung](https://support.office.com/en-us/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85).</span><span class="sxs-lookup"><span data-stu-id="b3d7e-111">For more information, see [Manage external sharing for your SharePoint Online environment](https://support.office.com/en-us/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85).</span></span>
    
  
- <span data-ttu-id="b3d7e-112">In Office 365-Gruppen: **Hinzufügen von Personen außerhalb der Organisation zu Gruppen durch Gruppenbesitzer zulassen**</span><span class="sxs-lookup"><span data-stu-id="b3d7e-112">In Office 365 groups: **Let group owners add people outside the organization to groups**</span></span>
    
    <span data-ttu-id="b3d7e-113">Weitere Informationen finden Sie unter [Steuern des Gastzugriffs auf Microsoft Teams](#controlguest).</span><span class="sxs-lookup"><span data-stu-id="b3d7e-113">For more information, see [Control guest access to Microsoft Teams](#controlguest).</span></span>
  

<span data-ttu-id="b3d7e-114">Sie können SharePoint Online-Einstellungen für externe Benutzer für die mit Microsoft Teams verbundene Teamwebsite verwalten.</span><span class="sxs-lookup"><span data-stu-id="b3d7e-114">Yes, you can manage SharePoint Online external user settings for the Teams connected team site.</span></span> <span data-ttu-id="b3d7e-115">Weitere Einzelheiten finden Sie unter [Verwalten der Einstellungen Ihrer SharePoint-Teamwebsite](https://support.office.com/en-us/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).</span><span class="sxs-lookup"><span data-stu-id="b3d7e-115">For more details, see  [Manage your SharePoint team site settings](https://support.office.com/en-us/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).</span></span>