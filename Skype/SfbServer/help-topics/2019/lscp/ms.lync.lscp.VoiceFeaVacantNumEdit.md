---
title: Nicht zugewiesene Telefonnummer Erstellen einer neuen oder Bearbeiten einer vorhandenen
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
ROBOTS: NOINDEX, NOFOLLOW
description: Nicht zugewiesene Nummern sind Rufnummern, die für Ihre Organisation gültig sind, jedoch keinem Benutzer oder Telefon zugewiesen sind. In der Tabelle mit den nicht zugewiesenen Nummern ist angegeben, wie Anrufe bei nicht zugewiesenen Nummern behandelt werden sollen.
ms.openlocfilehash: f4428a0f3ec5e1da5267c23f9064815206262893
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373843"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a><span data-ttu-id="80613-104">Nicht zugewiesene Telefonnummer: Erstellen Sie einer neuen oder bearbeiten Sie einer vorhandenen</span><span class="sxs-lookup"><span data-stu-id="80613-104">Unassigned Phone Number: Create New or Edit Existing</span></span>

> [!NOTE]
> <span data-ttu-id="80613-105">Exchange UM bleibt verfügbar in Skype für Business Server 2019 beim Exchange 2013 oder Exchange 2016 Skype für Unternehmen 2019 integrieren.</span><span class="sxs-lookup"><span data-stu-id="80613-105">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="80613-106">Aufgrund von Änderungen im-Unterstützung in Exchange 2019 wird aufgehoben wird Cloud Voicemail und Cloud-Telefonzentrale Features emphasised Exchange UM-Integration.</span><span class="sxs-lookup"><span data-stu-id="80613-106">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasised in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>

<span data-ttu-id="80613-p103">Nicht zugewiesene Nummern sind Rufnummern, die für Ihre Organisation gültig sind, jedoch keinem Benutzer oder Telefon zugewiesen sind. In der Tabelle mit den nicht zugewiesenen Nummern ist angegeben, wie Anrufe bei nicht zugewiesenen Nummern behandelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="80613-p103">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="80613-109">Wenn Sie einen neuen Bereichs nicht zugewiesenen Nummern erstellen oder Bearbeiten einer vorhandenen fertig sind, klicken Sie auf **OK** , um zur Seite **Nicht zugewiesene Nummer** zurückzugeben, die alle Bereiche auflistet.</span><span class="sxs-lookup"><span data-stu-id="80613-109">When you are finished creating a new unassigned number range or editing an existing one, click **OK** to return to the **Unassigned Number** page that lists all the number ranges.</span></span> <span data-ttu-id="80613-110">Die Änderungen, die Sie auf der Seite **Neu Unassigned Number Range** oder die **Rage für nicht zugewiesene Nummer bearbeiten** vorgenommen sind nicht in die Datenbank übernommen, bis Sie **Alle Commit** klicken Sie auf der Seite **Nicht zugewiesene Nummer** auf.</span><span class="sxs-lookup"><span data-stu-id="80613-110">The changes you made on the **New Unassigned Number Range** page or the **Edit Unassigned Number Rage** page are not committed to the database until you click **Commit all** on the **Unassigned Number** page.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="80613-111">Referenz zur Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="80613-111">UI Reference</span></span>

<span data-ttu-id="80613-112">In der folgenden Liste werden die Felder der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="80613-112">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="80613-113">**Name** Geben Sie einen beschreibenden Namen, der den nicht zugewiesenen Nummernbereich.</span><span class="sxs-lookup"><span data-stu-id="80613-113">**Name** Type a descriptive name that identifies the unassigned number range.</span></span> <span data-ttu-id="80613-114">Nachdem Sie den Bereich gespeichert haben, kann dieser Name geändert werden.</span><span class="sxs-lookup"><span data-stu-id="80613-114">After you save the range, this name cannot be changed.</span></span>

- <span data-ttu-id="80613-115">**Zahlenbereich** Geben Sie im ersten Feld die Anfangsnummer des Bereichs nicht zugewiesener Nummern.</span><span class="sxs-lookup"><span data-stu-id="80613-115">**Number range** In the first field, type the beginning number of the unassigned number range.</span></span> <span data-ttu-id="80613-116">Geben Sie in das zweite Feld die Endnummer des Bereichs.</span><span class="sxs-lookup"><span data-stu-id="80613-116">In the second field, type the ending number of the range.</span></span>

  - <span data-ttu-id="80613-117">Die Startnummer für den Bereich muss kleiner oder gleich der Endnummer sein.</span><span class="sxs-lookup"><span data-stu-id="80613-117">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="80613-118">Wenn die erste Nummer im Bereich oder die letzte Nummer im Bereich eine Durchwahl umfassen, müssen sowohl die erste als auch die letzte Nummer im Bereich einen Durchwahl aufweisen und die Durchwahlnummer muss für die erste und die letzte Nummer übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="80613-118">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>

  - <span data-ttu-id="80613-119">Die Anzahl muss mit den regulären Ausdruck übereinstimmen (tel:) ? (\+) [1-9] ? \d{0,17}(; Ext = [1-9] \d{0,9}) ?.</span><span class="sxs-lookup"><span data-stu-id="80613-119">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="80613-120">Dies bedeutet, dass die Anzahl beginnt mit der Zeichenfolge tel: (Wenn Sie nicht, dass diese Zeichenfolge angeben es wird automatisch hinzugefügt werden für Sie), ein Pluszeichen (+) sowie ein Zahl von 1 bis 9.</span><span class="sxs-lookup"><span data-stu-id="80613-120">This means the number may begin with the string tel: (if you don't specify that string it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="80613-121">Die Telefonnummer kann bis zu 17 Zeichen umfassen, gefolgt von einer Durchwahl im Format ";ext=" plus der Durchwahlnummer.</span><span class="sxs-lookup"><span data-stu-id="80613-121">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>

- <span data-ttu-id="80613-122">**Konferenzankündigungsdienst** Wählen Sie **Ankündigung** die ankündigungsanwendung den eingehenden Anruf behandeln sein oder **Exchange UM** für eine automatische Telefonzentrale von Exchange UM den eingehenden Anruf behandeln haben.</span><span class="sxs-lookup"><span data-stu-id="80613-122">**Announcement service** Select **Announcement** to have the Announcement application handle the incoming call or **Exchange UM** to have an Exchange UM Auto Attendant handle the incoming call.</span></span>

- <span data-ttu-id="80613-123">Wenn Sie eine **Ankündigung** für **Ankündigungsdienst**ausgewählt haben:</span><span class="sxs-lookup"><span data-stu-id="80613-123">If you selected **Announcement** for **Announcement service**:</span></span>

  - <span data-ttu-id="80613-124">**FQDN des Zielservers** Wählen Sie die Dienst-ID des Anwendungsdiensts, der die ankündigungsanwendung ausgeführt wird, die eingehende Anrufe für diesen Bereich nicht zugewiesener Nummern behandelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="80613-124">**FQDN of destination server** Select the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

  - <span data-ttu-id="80613-125">**Ankündigung** Wählen Sie die Ankündigung für diesen Bereich nicht zugewiesener Nummern wiedergegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="80613-125">**Announcement** Select the announcement to be played for this range of unassigned numbers.</span></span>

- <span data-ttu-id="80613-126">Wenn Sie **Exchange UM** für **Ankündigungsdienst**ausgewählt haben:</span><span class="sxs-lookup"><span data-stu-id="80613-126">If you selected **Exchange UM** for **Announcement service**:</span></span>

  - <span data-ttu-id="80613-127">**Telefonnummer der automatischen Telefonzentrale** Wählen Sie die Telefonnummer für die Exchange UM-Telefonzentrale aus.</span><span class="sxs-lookup"><span data-stu-id="80613-127">**Auto Attendant phone number** Select the phone number for the Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="80613-128">Ausführliche Informationen zur Ankündigung Features und Funktionen finden Sie unter [Planen für die ankündigungsanwendung in Skype für Unternehmen](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="80613-128">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="80613-129">Ausführliche Informationen zur Verwendung von nicht zugewiesenen Nummernbereiche finden Sie unter [Konfigurieren von Routing von nicht zugewiesenen Telefonnummern](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="80613-129">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>


