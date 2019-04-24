---
title: Nicht zugewiesene Telefonnummer Erstellen einer neuen oder Bearbeiten einer vorhandenen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
description: Nicht zugewiesene Nummern sind Rufnummern, die für Ihre Organisation gültig sind, jedoch keinem Benutzer oder Telefon zugewiesen sind. In der Tabelle mit den nicht zugewiesenen Nummern ist angegeben, wie Anrufe bei nicht zugewiesenen Nummern behandelt werden sollen.
ms.openlocfilehash: 3091ae34eee6e877079c927e087789d910d1bf7f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219936"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a><span data-ttu-id="f2b1d-104">Nicht zugewiesene Telefonnummer: Erstellen einer neuen oder Bearbeiten einer vorhandenen nicht zugewiesenen Nummer</span><span class="sxs-lookup"><span data-stu-id="f2b1d-104">Unassigned Phone Number: Create New or Edit Existing</span></span>

<span data-ttu-id="f2b1d-p102">Nicht zugewiesene Nummern sind Rufnummern, die für Ihre Organisation gültig sind, jedoch keinem Benutzer oder Telefon zugewiesen sind. In der Tabelle mit den nicht zugewiesenen Nummern ist angegeben, wie Anrufe bei nicht zugewiesenen Nummern behandelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f2b1d-p102">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f2b1d-107">Wenn Sie einen neuen Bereichs nicht zugewiesenen Nummern erstellen oder Bearbeiten einer vorhandenen fertig sind, klicken Sie auf **OK** , um zur Seite **Nicht zugewiesene Nummer** zurückzugeben, die alle Bereiche auflistet.</span><span class="sxs-lookup"><span data-stu-id="f2b1d-107">When you are finished creating a new unassigned number range or editing an existing one, click **OK** to return to the **Unassigned Number** page that lists all the number ranges.</span></span> <span data-ttu-id="f2b1d-108">Die Änderungen, die Sie auf der Seite **Neu Unassigned Number Range** oder die **Rage für nicht zugewiesene Nummer bearbeiten** vorgenommen sind nicht in die Datenbank übernommen, bis Sie **Alle Commit** klicken Sie auf der Seite **Nicht zugewiesene Nummer** auf.</span><span class="sxs-lookup"><span data-stu-id="f2b1d-108">The changes you made on the **New Unassigned Number Range** page or the **Edit Unassigned Number Rage** page are not committed to the database until you click **Commit all** on the **Unassigned Number** page.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="f2b1d-109">Referenz zur Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="f2b1d-109">UI Reference</span></span>

<span data-ttu-id="f2b1d-110">In der folgenden Liste werden die Felder der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f2b1d-110">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="f2b1d-111">**Name** Geben Sie einen beschreibenden Namen, der den nicht zugewiesenen Nummernbereich.</span><span class="sxs-lookup"><span data-stu-id="f2b1d-111">**Name** Type a descriptive name that identifies the unassigned number range.</span></span> <span data-ttu-id="f2b1d-112">Nachdem Sie den Bereich gespeichert haben, kann dieser Name geändert werden.</span><span class="sxs-lookup"><span data-stu-id="f2b1d-112">After you save the range, this name cannot be changed.</span></span>

- <span data-ttu-id="f2b1d-113">**Zahlenbereich** Geben Sie im ersten Feld die Anfangsnummer des Bereichs nicht zugewiesener Nummern.</span><span class="sxs-lookup"><span data-stu-id="f2b1d-113">**Number range** In the first field, type the beginning number of the unassigned number range.</span></span> <span data-ttu-id="f2b1d-114">Geben Sie in das zweite Feld die Endnummer des Bereichs.</span><span class="sxs-lookup"><span data-stu-id="f2b1d-114">In the second field, type the ending number of the range.</span></span>

  - <span data-ttu-id="f2b1d-115">Die Startnummer für den Bereich muss kleiner oder gleich der Endnummer sein.</span><span class="sxs-lookup"><span data-stu-id="f2b1d-115">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="f2b1d-116">Wenn die erste Nummer im Bereich oder die letzte Nummer im Bereich eine Durchwahl umfassen, müssen sowohl die erste als auch die letzte Nummer im Bereich einen Durchwahl aufweisen und die Durchwahlnummer muss für die erste und die letzte Nummer übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="f2b1d-116">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>

  - <span data-ttu-id="f2b1d-117">Die Anzahl muss mit den regulären Ausdruck übereinstimmen (tel:) ? (\+) [1-9] ? \d{0,17}(; Ext = [1-9] \d{0,9}) ?.</span><span class="sxs-lookup"><span data-stu-id="f2b1d-117">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="f2b1d-118">Dies bedeutet, dass die Anzahl beginnt mit der Zeichenfolge tel: (Wenn Sie nicht, dass diese Zeichenfolge angeben es wird automatisch hinzugefügt werden für Sie), ein Pluszeichen (+) sowie ein Zahl von 1 bis 9.</span><span class="sxs-lookup"><span data-stu-id="f2b1d-118">This means the number may begin with the string tel: (if you don't specify that string it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="f2b1d-119">Die Telefonnummer kann bis zu 17 Zeichen umfassen, gefolgt von einer Durchwahl im Format ";ext=" plus der Durchwahlnummer.</span><span class="sxs-lookup"><span data-stu-id="f2b1d-119">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>

- <span data-ttu-id="f2b1d-120">**Konferenzankündigungsdienst** Wählen Sie **Ankündigung** die ankündigungsanwendung den eingehenden Anruf behandeln sein oder **Exchange UM** für eine automatische Telefonzentrale von Exchange UM den eingehenden Anruf behandeln haben.</span><span class="sxs-lookup"><span data-stu-id="f2b1d-120">**Announcement service** Select **Announcement** to have the Announcement application handle the incoming call or **Exchange UM** to have an Exchange UM Auto Attendant handle the incoming call.</span></span>

- <span data-ttu-id="f2b1d-121">Wenn Sie eine **Ankündigung** für **Ankündigungsdienst**ausgewählt haben:</span><span class="sxs-lookup"><span data-stu-id="f2b1d-121">If you selected **Announcement** for **Announcement service**:</span></span>

  - <span data-ttu-id="f2b1d-122">**FQDN des Zielservers** Wählen Sie die Dienst-ID des Anwendungsdiensts, der die ankündigungsanwendung ausgeführt wird, die eingehende Anrufe für diesen Bereich nicht zugewiesener Nummern behandelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f2b1d-122">**FQDN of destination server** Select the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

  - <span data-ttu-id="f2b1d-123">**Ankündigung** Wählen Sie die Ankündigung für diesen Bereich nicht zugewiesener Nummern wiedergegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="f2b1d-123">**Announcement** Select the announcement to be played for this range of unassigned numbers.</span></span>

- <span data-ttu-id="f2b1d-124">Wenn Sie **Exchange UM** für **Ankündigungsdienst**ausgewählt haben:</span><span class="sxs-lookup"><span data-stu-id="f2b1d-124">If you selected **Exchange UM** for **Announcement service**:</span></span>

  - <span data-ttu-id="f2b1d-125">**Telefonnummer der automatischen Telefonzentrale** Wählen Sie die Telefonnummer für die Exchange UM-Telefonzentrale aus.</span><span class="sxs-lookup"><span data-stu-id="f2b1d-125">**Auto Attendant phone number** Select the phone number for the Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="f2b1d-126">Ausführliche Informationen zur Ankündigung Features und Funktionen finden Sie unter [Planen für die ankündigungsanwendung in Skype für Business 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="f2b1d-126">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="f2b1d-127">Ausführliche Informationen zur Verwendung von Bereichen nicht zugewiesener Nummern finden Sie in der Betriebsdokumentation unter [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx).</span><span class="sxs-lookup"><span data-stu-id="f2b1d-127">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>


