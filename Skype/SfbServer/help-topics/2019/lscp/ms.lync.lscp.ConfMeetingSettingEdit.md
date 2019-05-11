---
title: Besprechungskonfiguration Erstellen einer neuen oder Bearbeiten einer vorhandenen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
ROBOTS: NOINDEX, NOFOLLOW
description: Mithilfe von Konfigurationseinstellungen für Besprechungen wird der Benutzerbeitritt für von Benutzern geplante Konferenzen definiert. Diese Einstellungen gelten nur für geplante Besprechungen. Sie gelten nicht für Ad-hoc-Besprechungen, die durch Klicken auf die Option Sofortbesprechung erstellt werden.
ms.openlocfilehash: 05613fb9c8df89bb9c7efc5fe7bfced78ca12574
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33891586"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a><span data-ttu-id="fa60e-105">Besprechungskonfiguration: Erstellen einer neuen oder Bearbeiten einer vorhandenen Besprechungskonfiguration</span><span class="sxs-lookup"><span data-stu-id="fa60e-105">Meeting Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="fa60e-p102">Mithilfe von Konfigurationseinstellungen für Besprechungen wird der Benutzerbeitritt für von Benutzern geplante Konferenzen definiert. Diese Einstellungen gelten nur für geplante Besprechungen. Sie gelten nicht für Ad-hoc-Besprechungen, die durch Klicken auf die Option **Sofortbesprechung** erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="fa60e-p102">Meeting configuration settings define the user join experience for conferences scheduled by users. These settings only apply to scheduled meetings. They do not apply to ad-hoc meetings created by clicking the **Meet Now** option in the client.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="fa60e-109">Referenz zur Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="fa60e-109">UI Reference</span></span>

<span data-ttu-id="fa60e-110">In der folgenden Liste werden die Felder der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fa60e-110">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="fa60e-111">**Bereich** Gibt den Bereich der besprechungskonfiguration, die Sie erstellen oder ändern: global, Standort oder Pool.</span><span class="sxs-lookup"><span data-stu-id="fa60e-111">**Scope** Identifies the scope of the meeting configuration that you are creating or modifying: global, site, or pool.</span></span>

- <span data-ttu-id="fa60e-112">**Name** Besprechungskonfigurationen erhalten standardmäßig, und der Name kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="fa60e-112">**Name** Meeting configurations are named by default, and the name cannot be changed.</span></span>

- <span data-ttu-id="fa60e-113">**PSTN-Anrufer umgehen die lobby** Aktivieren Sie dieses Kontrollkästchen, um automatisch Benutzer, die in einwählen, um der Konferenz über eine public switched Telephone Network, (PSTN) Telefonleitung zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="fa60e-113">**PSTN callers bypass lobby** Select this check box to automatically admit users who are dialing in to the conference over a public switched telephone network (PSTN) phone line.</span></span> <span data-ttu-id="fa60e-114">Deaktivieren Sie dieses Kontrollkästchen, um PSTN-Anrufer in den Konferenzwartebereich weiterzuleiten und dort zu halten, bis ihnen der Konferenzreferent Zugang zur Besprechung gewährt.</span><span class="sxs-lookup"><span data-stu-id="fa60e-114">Clear this check box to route PSTN callers to the conference lobby, where they are on hold until a conference presenter grants them access to the conference.</span></span>

- <span data-ttu-id="fa60e-115">**Legen Sie als Referent** Wählen Sie die Kategorie von Benutzern (außer dem Organisator der Besprechung), die automatisch als Referenten festgelegt werden, wenn sie an eine Konferenz teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="fa60e-115">**Designate as presenter** Select the category of users (besides the meeting organizer) who are automatically designated as presenters when they join a conference.</span></span> <span data-ttu-id="fa60e-116">Unabhängig von dieser Einstellung können Benutzer explizit als Referenten festgelegt werden, wenn die Konferenz geplant wird, oder sie können während der Konferenz explizit zu Referenten ernannt werden.</span><span class="sxs-lookup"><span data-stu-id="fa60e-116">Regardless of this setting, presenters can be explicitly designated as presenters when the conference is scheduled, or they can be explicitly promoted to presenter during the conference.</span></span> <span data-ttu-id="fa60e-117">Mögliche Optionen:</span><span class="sxs-lookup"><span data-stu-id="fa60e-117">The options are:</span></span>

  - <span data-ttu-id="fa60e-118">**None** Wählen Sie diese Option aus, wenn keine andere Person als der Organisator automatisch als Referent festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="fa60e-118">**None** Select this option if no one other than the organizer is automatically designated as a presenter.</span></span>

  - <span data-ttu-id="fa60e-119">**Unternehmen** Wählen Sie diese Option, um nur Mitglieder Ihrer Organisation automatisch als Referenten festzulegen.</span><span class="sxs-lookup"><span data-stu-id="fa60e-119">**Company** Select this option to automatically designate only members of your organization as presenters.</span></span>

  - <span data-ttu-id="fa60e-120">**Jeder** Wählen Sie diese Option, um automatisch alle Personen als Referenten festzulegen.</span><span class="sxs-lookup"><span data-stu-id="fa60e-120">**Everyone** Select this option to automatically designate anyone to be a presenter.</span></span>

- <span data-ttu-id="fa60e-121">**Konferenztyp standardmäßig zugewiesen** Dieser Einstellung wird gesteuert, ob das Outlook-Add-Konferenzen immer Konferenzen plant mithilfe der Organisator Konferenz zugewiesen, haben, d. h., die immer Konferenzen geplant, die dieselbe Join-URL und Zugriffsinformationen enthalten.</span><span class="sxs-lookup"><span data-stu-id="fa60e-121">**Assigned conference type by default** This setting controls whether the Outlook Conferencing Addin always schedules conferences by using the organizer's assigned conference, which means that scheduled conferences always have the same join URL and audio information.</span></span> <span data-ttu-id="fa60e-122">Aktivieren Sie dieses Kontrollkästchen, geplante Konferenzen verwenden Sie dieselbe URL Join immer haben.</span><span class="sxs-lookup"><span data-stu-id="fa60e-122">Select this check box to have scheduled conferences always use the same join URL.</span></span> <span data-ttu-id="fa60e-123">Deaktivieren Sie dieses Kontrollkästchen, um einen anderen Join-URL für jede Konferenz verwenden.</span><span class="sxs-lookup"><span data-stu-id="fa60e-123">Clear this check box to use a different join URL for each conference.</span></span>

- <span data-ttu-id="fa60e-124">**Anonyme Benutzer zulassen, standardmäßig** Aktivieren Sie dieses Kontrollkästchen, wenn anonyme (d. h., nicht authentifizierte) Benutzer an Konferenzen teilnehmen in der Standardeinstellung zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="fa60e-124">**Admit anonymous users by default** Select this check box if anonymous (that is, unauthenticated) users are allowed to attend conferences by default.</span></span> <span data-ttu-id="fa60e-125">Deaktivieren Sie dieses Kontrollkästchen, wenn anonyme Benutzer nicht standardmäßig zu Konferenzen zugelassen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="fa60e-125">Clear this check box if anonymous users are not allowed to attend conferences by default.</span></span>

- <span data-ttu-id="fa60e-126">**Logo-URL** Geben Sie die URL mit dem Bild für benutzerdefinierte konferenzeinladungen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="fa60e-126">**Logo URL** Type the URL that has the image to be used for custom conference invitations.</span></span>

- <span data-ttu-id="fa60e-127">**Hilfe-URL** Geben Sie die URL für eine Website, in dem Benutzer Hilfe zur Teilnahme an der Konferenz erhalten können.</span><span class="sxs-lookup"><span data-stu-id="fa60e-127">**Help URL** Type the URL for a website where users can obtain assistance for joining the conference.</span></span>

- <span data-ttu-id="fa60e-128">**URL zu rechtlichen** Geben Sie die URL für eine Website, die die rechtliche Hinweise und Haftungsausschlüsse für die Konferenz.</span><span class="sxs-lookup"><span data-stu-id="fa60e-128">**Legal text URL** Type the URL for a website that has the legal information and disclaimers for the conference.</span></span>

- <span data-ttu-id="fa60e-129">**Benutzerdefinierter Fußzeilentext text** Geben Sie den Text für benutzerdefinierte konferenzeinladungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fa60e-129">**Custom footer text** Type the text to be used on custom conference invitations.</span></span>

<span data-ttu-id="fa60e-p107">Ausführliche Informationen zur Verwendung von Besprechungskonfigurationen finden Sie in der Betriebsdokumentation unter [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx). Ausführliche Informationen zur Festlegung von Besprechungskonfigurationen für große Besprechungen finden Sie in der Planungsdokumentation unter [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx).</span><span class="sxs-lookup"><span data-stu-id="fa60e-p107">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) in the Operations documentation. For details about setting meeting configurations for large meetings, see [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) in the Planning documentation.</span></span>


