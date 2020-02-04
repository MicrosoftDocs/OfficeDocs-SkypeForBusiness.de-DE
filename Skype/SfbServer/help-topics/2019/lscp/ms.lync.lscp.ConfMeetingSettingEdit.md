---
title: Besprechungskonfiguration neues erstellen oder vorhandenes bearbeiten
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
ROBOTS: NOINDEX, NOFOLLOW
description: Mithilfe von Konfigurationseinstellungen für Besprechungen wird der Benutzerbeitritt für von Benutzern geplante Konferenzen definiert. Diese Einstellungen gelten nur für geplante Besprechungen. Sie gelten nicht für Ad-hoc-Besprechungen, die durch Klicken auf die Option Sofortbesprechung erstellt werden.
ms.openlocfilehash: ce94eff347d4cbae35d78ced44873e8164abe0d5
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41691400"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a><span data-ttu-id="91c1c-105">Besprechungskonfiguration: Erstellen einer neuen oder Bearbeiten einer vorhandenen Besprechungskonfiguration</span><span class="sxs-lookup"><span data-stu-id="91c1c-105">Meeting Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="91c1c-p102">Mithilfe von Konfigurationseinstellungen für Besprechungen wird der Benutzerbeitritt für von Benutzern geplante Konferenzen definiert. Diese Einstellungen gelten nur für geplante Besprechungen. Sie gelten nicht für Ad-hoc-Besprechungen, die durch Klicken auf die Option **Sofortbesprechung** erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="91c1c-p102">Meeting configuration settings define the user join experience for conferences scheduled by users. These settings only apply to scheduled meetings. They do not apply to ad-hoc meetings created by clicking the **Meet Now** option in the client.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="91c1c-109">Referenz zur Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="91c1c-109">UI Reference</span></span>

<span data-ttu-id="91c1c-110">In der folgenden Liste werden die Felder der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="91c1c-110">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="91c1c-111">**Bereich** Identifiziert den Bereich der zu erstellende oder zu ändernden besprechungskonfiguration: Global, Site oder Pool.</span><span class="sxs-lookup"><span data-stu-id="91c1c-111">**Scope** Identifies the scope of the meeting configuration that you are creating or modifying: global, site, or pool.</span></span>

- <span data-ttu-id="91c1c-112">**Name** Besprechungs Konfigurationen werden standardmäßig benannt, und der Name kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="91c1c-112">**Name** Meeting configurations are named by default, and the name cannot be changed.</span></span>

- <span data-ttu-id="91c1c-113">**PSTN-Anrufer Bypass-Lobby** Aktivieren Sie dieses Kontrollkästchen, um die Benutzer, die sich bei der Konferenz einwählen, über eine Telefonleitung des öffentlichen Telefonnetzes (PSTN) automatisch zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="91c1c-113">**PSTN callers bypass lobby** Select this check box to automatically admit users who are dialing in to the conference over a public switched telephone network (PSTN) phone line.</span></span> <span data-ttu-id="91c1c-114">Deaktivieren Sie dieses Kontrollkästchen, um PSTN-Anrufer in den Konferenzwartebereich weiterzuleiten und dort zu halten, bis ihnen der Konferenzreferent Zugang zur Besprechung gewährt.</span><span class="sxs-lookup"><span data-stu-id="91c1c-114">Clear this check box to route PSTN callers to the conference lobby, where they are on hold until a conference presenter grants them access to the conference.</span></span>

- <span data-ttu-id="91c1c-115">**Als Referent festlegen** Wählen Sie die Kategorie der Benutzer (außer dem Besprechungsorganisator) aus, die beim teilnehmen an einer Konferenz automatisch als Referenten festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="91c1c-115">**Designate as presenter** Select the category of users (besides the meeting organizer) who are automatically designated as presenters when they join a conference.</span></span> <span data-ttu-id="91c1c-116">Unabhängig von dieser Einstellung können Benutzer explizit als Referenten festgelegt werden, wenn die Konferenz geplant wird, oder sie können während der Konferenz explizit zu Referenten ernannt werden.</span><span class="sxs-lookup"><span data-stu-id="91c1c-116">Regardless of this setting, presenters can be explicitly designated as presenters when the conference is scheduled, or they can be explicitly promoted to presenter during the conference.</span></span> <span data-ttu-id="91c1c-117">Mögliche Optionen:</span><span class="sxs-lookup"><span data-stu-id="91c1c-117">The options are:</span></span>

  - <span data-ttu-id="91c1c-118">**Keine** Wählen Sie diese Option aus, wenn kein anderer als der Organisator automatisch als Referent festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="91c1c-118">**None** Select this option if no one other than the organizer is automatically designated as a presenter.</span></span>

  - <span data-ttu-id="91c1c-119">**Unternehmen** Wählen Sie diese Option aus, um nur Mitglieder Ihrer Organisation automatisch als Referenten festzulegen.</span><span class="sxs-lookup"><span data-stu-id="91c1c-119">**Company** Select this option to automatically designate only members of your organization as presenters.</span></span>

  - <span data-ttu-id="91c1c-120">**Alle Personen** Wählen Sie diese Option aus, um automatisch alle Personen als Referenten festzulegen.</span><span class="sxs-lookup"><span data-stu-id="91c1c-120">**Everyone** Select this option to automatically designate anyone to be a presenter.</span></span>

- <span data-ttu-id="91c1c-121">**Standardmäßig zugewiesene Konferenztypen** Mit dieser Einstellung wird gesteuert, ob das Outlook-Konferenz-Add-in Konferenzen immer mithilfe der zugewiesenen Konferenz des Organisators plant, was bedeutet, dass geplante Konferenzen immer über die gleiche URL-und Audioinformationen für die Teilnahme verfügen.</span><span class="sxs-lookup"><span data-stu-id="91c1c-121">**Assigned conference type by default** This setting controls whether the Outlook Conferencing Addin always schedules conferences by using the organizer's assigned conference, which means that scheduled conferences always have the same join URL and audio information.</span></span> <span data-ttu-id="91c1c-122">Aktivieren Sie dieses Kontrollkästchen, damit geplante Konferenzen immer dieselbe Join-URL verwenden.</span><span class="sxs-lookup"><span data-stu-id="91c1c-122">Select this check box to have scheduled conferences always use the same join URL.</span></span> <span data-ttu-id="91c1c-123">Deaktivieren Sie dieses Kontrollkästchen, um für jede Konferenz eine andere Join-URL zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="91c1c-123">Clear this check box to use a different join URL for each conference.</span></span>

- <span data-ttu-id="91c1c-124">**Standardmäßig anonyme Benutzer zulassen** Aktivieren Sie dieses Kontrollkästchen, wenn anonyme (nicht authentifizierte) Benutzer standardmäßig an Konferenzen teilnehmen dürfen.</span><span class="sxs-lookup"><span data-stu-id="91c1c-124">**Admit anonymous users by default** Select this check box if anonymous (that is, unauthenticated) users are allowed to attend conferences by default.</span></span> <span data-ttu-id="91c1c-125">Deaktivieren Sie dieses Kontrollkästchen, wenn anonyme Benutzer nicht standardmäßig zu Konferenzen zugelassen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="91c1c-125">Clear this check box if anonymous users are not allowed to attend conferences by default.</span></span>

- <span data-ttu-id="91c1c-126">**Logo-URL** Geben Sie die URL ein, die das Bild enthält, das für benutzerdefinierte Konferenzeinladungen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="91c1c-126">**Logo URL** Type the URL that has the image to be used for custom conference invitations.</span></span>

- <span data-ttu-id="91c1c-127">**Hilfe-URL** Geben Sie die URL für eine Website ein, auf der Benutzer Unterstützung für die Teilnahme an der Konferenz erhalten können.</span><span class="sxs-lookup"><span data-stu-id="91c1c-127">**Help URL** Type the URL for a website where users can obtain assistance for joining the conference.</span></span>

- <span data-ttu-id="91c1c-128">**URL für juristischen Text** Geben Sie die URL für eine Website mit den rechtlichen Informationen und Haftungsausschlüssen für die Konferenz ein.</span><span class="sxs-lookup"><span data-stu-id="91c1c-128">**Legal text URL** Type the URL for a website that has the legal information and disclaimers for the conference.</span></span>

- <span data-ttu-id="91c1c-129">**Benutzerdefinierter Fußzeilentext** Geben Sie den Text ein, der für benutzerdefinierte Konferenzeinladungen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="91c1c-129">**Custom footer text** Type the text to be used on custom conference invitations.</span></span>

<span data-ttu-id="91c1c-p107">Ausführliche Informationen zur Verwendung von Besprechungskonfigurationen finden Sie in der Betriebsdokumentation unter [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx). Ausführliche Informationen zur Festlegung von Besprechungskonfigurationen für große Besprechungen finden Sie in der Planungsdokumentation unter [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx).</span><span class="sxs-lookup"><span data-stu-id="91c1c-p107">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) in the Operations documentation. For details about setting meeting configurations for large meetings, see [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) in the Planning documentation.</span></span>


