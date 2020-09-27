---
title: Informationen für IT-Administratoren zum Microsoft Teams-für-RealWear-Client (Vorschau)
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Eine Erläuterung des Microsoft Teams-für-RealWear-Clients für IT-Administratoren.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: d72007a4bde0db2890a889580ee92c8dab72ad1e
ms.sourcegitcommit: 8924cd77923ca321de72edc3fed04425a4b13044
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "48262512"
---
# <a name="microsoft-teams-for-realwear"></a><span data-ttu-id="a0a0d-103">Microsoft Teams für RealWear</span><span class="sxs-lookup"><span data-stu-id="a0a0d-103">Microsoft Teams for RealWear</span></span>

<span data-ttu-id="a0a0d-104">Dieser Artikel befasst sich mit dem Microsoft Teams-Client für am Kopf getragene RealWear-Geräte.</span><span class="sxs-lookup"><span data-stu-id="a0a0d-104">This article covers the Microsoft Teams client for RealWear head-mounted wearables.</span></span> <span data-ttu-id="a0a0d-105">Mitarbeiter mit RealWear HMT-1 und HMT-1Z1 können nun über einen Videoanruf in Teams mit einem Remoteexperten zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="a0a0d-105">FirstLine Workers using RealWear HMT-1 and HMT-1Z1 can now collaborate with a remote expert using video calling on Teams.</span></span> <span data-ttu-id="a0a0d-106">Mithilfe einer sprachgesteuerten Benutzeroberfläche ermöglicht Teams für RealWear, dass Außendienstmitarbeiter die Hände jederzeit frei haben, während das Lagebewusstsein in lauten und gefährlichen Umgebungen aufrechterhalten wird.</span><span class="sxs-lookup"><span data-stu-id="a0a0d-106">Through a voice-controlled user interface, Teams for RealWear allows field workers to remain 100% hands-free while maintaining situational awareness in loud and hazardous environments.</span></span> <span data-ttu-id="a0a0d-107">Indem sie in Echtzeit zeigen, was sie sehen, können Außendienstmitarbeiter die Zeit zur Lösung von Problemen zu verkürzen und das Risiko eines teuren Ausfalls reduzieren.</span><span class="sxs-lookup"><span data-stu-id="a0a0d-107">By showing what they see in real-time, field workers can accelerate the time to resolve issues and reduce the risk of an expensive downtime.</span></span>

## <a name="how-to-deploy-microsoft-teams-for-realwear"></a><span data-ttu-id="a0a0d-108">Wie man Microsoft Teams für RealWear einsetzt</span><span class="sxs-lookup"><span data-stu-id="a0a0d-108">How to deploy Microsoft Teams for RealWear</span></span>

- <span data-ttu-id="a0a0d-109">RealWear-Geräte, die auf Version 11.2 oder höher aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="a0a0d-109">RealWear devices updated to release 11.2 or above.</span></span> <span data-ttu-id="a0a0d-110">Weitere Informationen finden Sie [hier](https://realwear.com/knowledge-center/configure-on-release-10/wireless-update/).</span><span class="sxs-lookup"><span data-stu-id="a0a0d-110">More information [here](https://realwear.com/knowledge-center/configure-on-release-10/wireless-update/).</span></span>
- <span data-ttu-id="a0a0d-111">Zugriff auf [RealWear Foresight-](https://cloud.realwear.com/) zur Verteilung des Microsoft Teams-Clients für RealWear.</span><span class="sxs-lookup"><span data-stu-id="a0a0d-111">Access to [RealWear Foresight](https://cloud.realwear.com/) for distributing the Microsoft Teams client for Realwear.</span></span>

## <a name="required-licenses"></a><span data-ttu-id="a0a0d-112">Erforderliche Lizenzen</span><span class="sxs-lookup"><span data-stu-id="a0a0d-112">Required Licenses</span></span>

<span data-ttu-id="a0a0d-113">Microsoft Teams-Lizenzen sind Bestandteil von Microsoft 365- und Office 365-Abonnements.</span><span class="sxs-lookup"><span data-stu-id="a0a0d-113">Microsoft Teams licenses are part of Microsoft 365 and Office 365 subscriptions.</span></span> <span data-ttu-id="a0a0d-114">Für die Nutzung von Teams für RealWear sind keine weiteren Lizenzen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a0a0d-114">No additional licensing is required to use Teams for RealWear.</span></span> <span data-ttu-id="a0a0d-115">Weitere Informationen zum Erhalten von Teams finden Sie unter [Wie erhalte ich Zugriff auf Microsoft Teams?](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b).</span><span class="sxs-lookup"><span data-stu-id="a0a0d-115">For more information about getting Teams, check out [How do I get access to Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b).</span></span>

## <a name="managing-realwear-devices"></a><span data-ttu-id="a0a0d-116">Verwalten von RealWear-Geräten</span><span class="sxs-lookup"><span data-stu-id="a0a0d-116">Managing RealWear devices</span></span>

### <a name="microsoft-endpoint-manager"></a><span data-ttu-id="a0a0d-117">Microsoft Endpunkt-Manager</span><span class="sxs-lookup"><span data-stu-id="a0a0d-117">Microsoft Endpoint Manager</span></span>

<span data-ttu-id="a0a0d-118">RealWear-Geräte können über den Modus „Android-Geräteadministrator“ verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="a0a0d-118">RealWear devices can be managed using Android Device Administrator mode.</span></span> <span data-ttu-id="a0a0d-119">Die Unterstützung für die Verwaltung über Android Enterprise ist begrenzt, da auf den Geräten derzeit keine Google Mobile-Dienste (GMS) zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="a0a0d-119">Support for management via Android Enterprise is limited, as the devices currently don't have Google Mobile Services (GMS) available.</span></span>

- <span data-ttu-id="a0a0d-120">Weitere Informationen zum Verwalten von RealWear-Geräten in Microsoft Endpoint Manager finden Sie unter [Registrierung von Android-Geräteadministratoren in Intune](https://docs.microsoft.com/mem/intune/enrollment/android-enroll-device-administrator).</span><span class="sxs-lookup"><span data-stu-id="a0a0d-120">To learn more about managing RealWear devices on Microsoft Endpoint Manager, see [Android device administrator enrollment in Intune](https://docs.microsoft.com/mem/intune/enrollment/android-enroll-device-administrator).</span></span>
- <span data-ttu-id="a0a0d-121">Weitere Informationen zu Richtlinien finden Sie unter [Verwenden von InTune in Umgebungen ohne Google Mobile Services](https://docs.microsoft.com/mem/intune/apps/manage-without-gms).</span><span class="sxs-lookup"><span data-stu-id="a0a0d-121">For more details on policies, see [How to use Intune in environments without Google Mobile Services](https://docs.microsoft.com/mem/intune/apps/manage-without-gms).</span></span>

### <a name="third-party-enterprise-mobility-managers-emms"></a><span data-ttu-id="a0a0d-122">Drittanbieter für Enterprise Mobility-Manager (EMMs)</span><span class="sxs-lookup"><span data-stu-id="a0a0d-122">Third-party Enterprise Mobility Managers (EMMs)</span></span>

<span data-ttu-id="a0a0d-123">Anleitungen zu EMM von Drittanbietern finden Sie unter [Unterstützte Enterprise Mobility-Verwaltungsanbieter](https://www.realwear.com/knowledge-center/configure-on-release-10/remote-from-a-web-browser/emm/).</span><span class="sxs-lookup"><span data-stu-id="a0a0d-123">For guidance on third-party EMMs, see [Supported Enterprise Mobility Management Providers](https://www.realwear.com/knowledge-center/configure-on-release-10/remote-from-a-web-browser/emm/).</span></span>

## <a name="end-user-content"></a><span data-ttu-id="a0a0d-124">Endbenutzer-Inhalte</span><span class="sxs-lookup"><span data-stu-id="a0a0d-124">End-user content</span></span>

<span data-ttu-id="a0a0d-125">Wenn Sie weitere Inhalte aus der Sicht des Endbenutzers lesen möchten, finden Sie diese unter [Verwenden von Microsoft Teams für RealWear](https://support.office.com/article/using-microsoft-teams-for-realwear-af20d232-d18c-476f-8031-843a4edccd5f).</span><span class="sxs-lookup"><span data-stu-id="a0a0d-125">For further reading on this from an end-user perspective, please check out [Using Microsoft Teams for RealWear](https://support.office.com/article/using-microsoft-teams-for-realwear-af20d232-d18c-476f-8031-843a4edccd5f).</span></span>
