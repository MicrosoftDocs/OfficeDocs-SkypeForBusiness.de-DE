---
title: Teams-Umgebung in einer Office 365 OneDrive und SharePoint Online Multi-Geo-fähigen Mandanteneinheit
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
description: Erfahren Sie mehr über die Verwendung von Teams in einer Office 365 OneDrive-und SharePoint Online-Multi-Geo-fähigen Mietdauer.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: de798e3e76b4c826cf5b235b61b3fe88e94ea1c7
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837695"
---
<a name="teams-experience-in-an-office-365-onedrive-and-sharepoint-online-multi-geo-enabled-tenancy"></a><span data-ttu-id="aa74d-103">Teams-Umgebung in einer Office 365 OneDrive und SharePoint Online Multi-Geo-fähigen Mandanteneinheit</span><span class="sxs-lookup"><span data-stu-id="aa74d-103">Teams experience in an Office 365 OneDrive and SharePoint Online Multi-Geo-enabled tenancy</span></span>
===========================================

<span data-ttu-id="aa74d-104">Microsoft Teams ist eine Gruppen-Chat-Software, der Hub für Teamarbeit in Office 365.</span><span class="sxs-lookup"><span data-stu-id="aa74d-104">Microsoft Teams is group chat software, the hub for teamwork in Office 365.</span></span> <span data-ttu-id="aa74d-105">Sie wird vom Office 365 Groups-Dienst zusammen mit SharePoint Online und OneDrive for Business für die Dateinutzung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="aa74d-105">It is powered by the Office 365 Groups service along with SharePoint Online and OneDrive for Business for its files experience.</span></span> <span data-ttu-id="aa74d-106">In einer OneDrive for Business/SharePoint Online-Multi-Geo-Mietdauer, in der der Mandant auf viele geografische Standorte wie Nordamerika, Europa und Australien ausgeweitet wird, ist die zugrunde liegende Datei Erfahrung Multi-Geo-bewusst, daher ist die Team Erfahrung mit der Datei Zusammenarbeit auch Multi-Geo-fähig.</span><span class="sxs-lookup"><span data-stu-id="aa74d-106">In a OneDrive for Business/SharePoint Online Multi-Geo tenancy, in which the tenant is extended to many geographic locations such as North America, Europe, and Australia, the underlying files experience is Multi-Geo aware, so the Teams experience with file collaboration is also Multi-Geo aware.</span></span> <span data-ttu-id="aa74d-107">Hierbei handelt es sich um eine der wichtigsten Spitzenfunktionen für Teams, um Dateien, die über mehrere GEOSS gehostet werden, in der nativen Datei Oberfläche zu beleben.</span><span class="sxs-lookup"><span data-stu-id="aa74d-107">This is a key leading-edge capability for Teams to surface files hosted across multiple Geos in its native files experience.</span></span>

<span data-ttu-id="aa74d-108">In einer contoso-Mietdauer mit Europa als Satelliten Geo und Nordamerika als zentrales Geo sieht ein europäischer Satelliten Benutzer beispielsweise seine OneDrive-Dateien im linken Bereich unter der Registerkarte "Dateien", obwohl die Dateien im Europa-Datenspeicherort und im United stat gehostet werden. Es ist der zentrale Standort des Mandanten.</span><span class="sxs-lookup"><span data-stu-id="aa74d-108">For example, in a Contoso tenancy with Europe as a satellite Geo and North America as the central Geo, a European satellite user will see his or her OneDrive files under the Files tab in left pane, although the files are hosted in the Europe data location and the United States is the tenant’s central location.</span></span> <span data-ttu-id="aa74d-109">Darüber hinaus kann der Benutzer auf die zuletzt verwendeten Dateien unter dem Blade für zuletzt verwendete Ansichten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="aa74d-109">Also, the user can access the most recently used files under the Recent view blade.</span></span> <span data-ttu-id="aa74d-110">Aktuelle Dateien enthalten möglicherweise Dateien, die für den Benutzer von Benutzern in anderen GEOS freigegeben wurden, und möglicherweise an anderen geografischen Standorten, auf die der Mandant erweitert wird.</span><span class="sxs-lookup"><span data-stu-id="aa74d-110">Recent files may include files shared with the user from users in other Geos and might be mastered in other Geo locations that the tenant is extended to.</span></span> 

<span data-ttu-id="aa74d-111">Die Gruppen Website eines bestimmten Teams ist auch Multi-Geo-fähig.</span><span class="sxs-lookup"><span data-stu-id="aa74d-111">A given Team’s group site is also Multi-Geo aware.</span></span> <span data-ttu-id="aa74d-112">Das heißt, wenn ein europäischer Satelliten Benutzer ein Team erstellt, wird die entsprechende Gruppen Website am Standort Europa erstellt, und die Dateien, die dieser Team Gruppe zugeordnet sind, werden an diesem Speicherort beibehalten.</span><span class="sxs-lookup"><span data-stu-id="aa74d-112">That is, if a European satellite user is creating a Team, the corresponding Groups site will be created in the Europe location and the files associated with that Team group will be kept at rest in that location.</span></span> <span data-ttu-id="aa74d-113">Alle nachfolgenden Erfahrungen, wie das Hochladen einer neuen Datei oder das Bearbeiten der Datei, werden auf diesen europäischen Standort ausgerichtet, wobei das Versprechen einer Daten Residency für diese Dateien bleibt.</span><span class="sxs-lookup"><span data-stu-id="aa74d-113">Any subsequent experiences, such as uploading a new file or editing the file, will be targeted to that European location, keeping the promise of data residency for those files.</span></span> <span data-ttu-id="aa74d-114">Dies ist möglich, wenn die zugrunde liegenden Foundation Office 365-Gruppen multigeo-fähig werden.</span><span class="sxs-lookup"><span data-stu-id="aa74d-114">This is all made possible by the underlying foundation Office 365 Groups becoming Multi-Geo aware.</span></span>

<span data-ttu-id="aa74d-115">Da es sich bei einer Multi-Geo-Mietdauer um einen einzigen globalen Mandanten handelt, können die Satelliten Nutzer während der @ Erwähnungen Ihre Kollegen aus der ganzen Welt sehen – ganz gleich, wo Sie sich befinden.</span><span class="sxs-lookup"><span data-stu-id="aa74d-115">Because a Multi-Geo tenancy is a single global tenant, during @ mentions satellite users will be able to see their colleagues from across the globe, no matter where they reside.</span></span> 

<span data-ttu-id="aa74d-116">Beachten Sie, dass Unterhaltungen in Chats und Besprechungsnotizen innerhalb der Teams nicht multigeo-fähig sind und alle nur innerhalb des zentralen Standorts des Mandanten aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="aa74d-116">Note that conversations in chats and meeting IM notes within the Teams experience are not Multi-Geo aware and are all kept only inside the central location of the tenant.</span></span> <span data-ttu-id="aa74d-117">In der Regel werden Chat Unterhaltungen nicht auf die Anforderungen von Daten Wohnsitz angewendet.</span><span class="sxs-lookup"><span data-stu-id="aa74d-117">Typically, chat conversations aren’t applied to data residency needs.</span></span>

<span data-ttu-id="aa74d-118">Weitere Informationen zu Office 365 Multi-Geo finden Sie auf der [Seite Microsoft Multi-Geo-Funktionen](https://aka.ms/multi-geo).</span><span class="sxs-lookup"><span data-stu-id="aa74d-118">For more information about Office 365 Multi-Geo, refer to the [Microsoft Multi-Geo capabilities page](https://aka.ms/multi-geo).</span></span>