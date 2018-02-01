---
title: Gastzugriff in Microsoft Teams
author: LaithAlShamri
ms.author: laal
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Gastzugriff in Microsoft Teams ermöglicht Teams in Ihrer Organisation, mit Personen außerhalb Ihrer Organisation zusammenzuarbeiten, indem ihnen Zugriff auf Teams und Kanäle gewährt wird."
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 07dbb6faca20fd39fc65c6508489500dda143040
ms.sourcegitcommit: d62b48ee2c21435555255afe78db6349139b070c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2018
---
<a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="dbe16-103">Gastzugriff in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dbe16-103">Guest access in Microsoft Teams</span></span>
======================================

<span data-ttu-id="dbe16-104">Der Gastzugriff ist neu in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="dbe16-104">Guest Access is new in Teams.</span></span> <span data-ttu-id="dbe16-105">Es handelt sich dabei um eine der meistgewünschten Funktionen.</span><span class="sxs-lookup"><span data-stu-id="dbe16-105">It’s one of the features customers asked for the most.</span></span> <span data-ttu-id="dbe16-106">Wir arbeiten noch daran und erweitern die Möglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="dbe16-106">We’re still working on it, enhancing its capabilities.</span></span> <span data-ttu-id="dbe16-107">So können Sie sich über unsere Fortschritte beim Gastzugriff auf dem Laufenden halten und uns Ihre Meinung sagen:</span><span class="sxs-lookup"><span data-stu-id="dbe16-107">Here’s how you can keep up with our progress on Guest Access and tell us your thoughts:</span></span>
- <span data-ttu-id="dbe16-108">Wenn Sie Probleme mit dem Gastzugriff haben, lesen Sie [Bekannte Probleme für Microsoft Teams](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="dbe16-108">If you’re having trouble with Guest Access, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="dbe16-109">Informationen zu geplanten neuen oder aktualisierten Funktionen finden Sie in der [Microsoft Teams-Roadmap](https://aka.ms/teamsroadmap).</span><span class="sxs-lookup"><span data-stu-id="dbe16-109">Find out about upcoming new or updated features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="dbe16-110">Teilen Sie uns auf der [Microsoft Teams-UserVoice](https://aka.ms/TeamsUserVoice)-Website Ihre Wünsche mit.</span><span class="sxs-lookup"><span data-stu-id="dbe16-110">Tell us what you want in  [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>
- <span data-ttu-id="dbe16-111">Berichten Sie unten im Abschnitt „Kommentare“ über Ihre Erfahrungen.</span><span class="sxs-lookup"><span data-stu-id="dbe16-111">Share your experience in the Comments section below.</span></span>


<span data-ttu-id="dbe16-112">Gastzugriff in Microsoft Teams ermöglicht Teams in Ihrer Organisation, mit Personen außerhalb Ihrer Organisation zusammenzuarbeiten, indem ihnen Zugriff auf Teams und Kanäle gewährt wird.</span><span class="sxs-lookup"><span data-stu-id="dbe16-112">Guest access in Microsoft Teams allows teams in your organization to collaborate with people outside your organization by granting them access to teams and channels.</span></span> 

<span data-ttu-id="dbe16-113">Gastzugriff ist in allen Office 365 Business Premium-, Office 365 Enterprise- und Office 365 Education-Abonnements enthalten.</span><span class="sxs-lookup"><span data-stu-id="dbe16-113">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="dbe16-114">Eine zusätzliche Office 365-Lizenz ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="dbe16-114">No additional Office 365 license is necessary.</span></span> <span data-ttu-id="dbe16-115">Der Gastzugriff ist eine Einstellung auf Mandantenebene in Microsoft Teams, die standardmäßig deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="dbe16-115">Guest access is a tenant-level setting in Microsoft Teams and is turned off by default.</span></span>


<span data-ttu-id="dbe16-116">Ein Gast ist kein Mitarbeiter, Schüler/Student oder Mitglied Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="dbe16-116">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="dbe16-117">Er verfügt über kein Geschäfts-, Schul- oder Unikonto bei Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="dbe16-117">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="dbe16-118">Gäste können beispielsweise Partner, Hersteller, Lieferanten oder Berater sein.</span><span class="sxs-lookup"><span data-stu-id="dbe16-118">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="dbe16-119">Nur Benutzer, die über eine E-Mail-Adresse verfügen, die einem Azure Active Directory- oder Office 365-Geschäfts-, Schul- oder Unikonto entspricht, können als Gastbenutzer hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="dbe16-119">Only users who have an email address corresponding to an Azure Active Directory or Office 365 work or school account can be added as a guest user.</span></span>
  
       

<span data-ttu-id="dbe16-120">Organisationen, die Teams verwenden, können ihren Partnern externen Zugriff auf Teams, Dokumente in Kanälen, Ressourcen, Chats und Anwendungen gewähren und gleichzeitig die vollständige Kontrolle über ihre eigenen Unternehmensdaten behalten.</span><span class="sxs-lookup"><span data-stu-id="dbe16-120">Organizations using Teams can provide external access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span>

<span data-ttu-id="dbe16-121">Teams basiert auf Office 365-Gruppen und bietet neue Möglichkeiten, auf freigegebene Ressourcen für eine Office 365-Gruppe zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="dbe16-121">Teams is built upon Office 365 Groups and provides a new way to access shared assets for an Office 365 group.</span></span> <span data-ttu-id="dbe16-122">Teams ist die beste Lösung für beständigen Chat zwischen Gruppen- bzw. Teammitgliedern.</span><span class="sxs-lookup"><span data-stu-id="dbe16-122">Teams is the best solution for persistent chat among group/team members.</span></span> <span data-ttu-id="dbe16-123">Office 365-Gruppen ist ein Dienst, der anwendungsübergreifende Mitgliedschaft für bestimmte freigegebene Teamressourcen (beispielsweise eine SharePoint-Website oder ein Power BI-Dashboard) bietet, damit das Team effektiv und sicher zusammenarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="dbe16-123">Office 365 Groups is a service that provides cross-application membership for a set of shared team assets, like a SharePoint site or a Power BI dashboard, so that the team can collaborate effectively and securely.</span></span>

    

## <a name="more-information"></a><span data-ttu-id="dbe16-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dbe16-124">More information</span></span>

 
  
    
  [<span data-ttu-id="dbe16-125">Supportressourcen für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dbe16-125">Support resources for Microsoft Teams</span></span>](support-resources.md)  
 
  

    

  
|  |  |
|---------|---------|
| <span data-ttu-id="dbe16-126">Deep Dive into Guest Access (Tiefe Einblicke in die Gastzugriffsfunktion)</span><span class="sxs-lookup"><span data-stu-id="dbe16-126">Deep Dive into Guest Access</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/D8DW2Urv5y8" frameborder="0" allowfullscreen></iframe>   |
| <span data-ttu-id="dbe16-127">Aktivieren des Gastzugriffs in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dbe16-127">Enabling Guest Access in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/7T54KmlIHQk" frameborder="0" allowfullscreen></iframe>   |
 | <span data-ttu-id="dbe16-128">Hinzufügen von Gästen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dbe16-128">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
    

