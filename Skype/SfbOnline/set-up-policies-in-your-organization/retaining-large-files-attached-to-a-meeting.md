---
title: "Beibehaltung große Dateien, einen Skype für Business Besprechung zugeordnet ist"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: brendonb, markjjo
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 12203a1a-4a9f-4838-88c5-3740ea16ed8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: "Sie können Dateien an einen Skype für Business-Besprechung anfügen, welche Teilnehmer können dann öffnen und herunterladen. Anlagen von Skype für Business Besprechungen werden in die Postfächer der alle Teilnehmer beibehalten, dessen Postfach beweissicherungsverfahrens platziert wird, verfügt über ein Office 365-Aufbewahrungsrichtlinie angewendet oder befindet sich in einem Haltestatus Zusammenhang mit einem eDiscovery-Fall in die Office 365-Sicherheit &amp; Compliance Center. Dieser Inhalt wird zum Umschalten wiederherstellbare Elemente Ordner in ihren Postfächern gespeichert."
ms.openlocfilehash: fb20055106362143b5c4573115e095637d873599
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2018
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a><span data-ttu-id="132f8-105">Beibehaltung große Dateien, einen Skype für Business Besprechung zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="132f8-105">Retaining large files attached to a Skype for Business meeting</span></span>

<span data-ttu-id="132f8-106">Sie können Dateien an einen Skype für Business-Besprechung anfügen, welche Teilnehmer können dann öffnen und herunterladen.</span><span class="sxs-lookup"><span data-stu-id="132f8-106">You can attach files to a Skype for Business meeting, which participants can then open and download.</span></span> <span data-ttu-id="132f8-107">Anlagen von Skype für Business Besprechungen werden in die Postfächer der alle Teilnehmer beibehalten, dessen Postfach beweissicherungsverfahrens platziert wird, verfügt über ein Office 365-Aufbewahrungsrichtlinie angewendet oder befindet sich in einem Haltestatus Zusammenhang mit einem eDiscovery-Fall in die Office 365-Sicherheit &amp; Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="132f8-107">Files attached to Skype for Business meetings are retained in the mailboxes of any participant whose mailbox is placed on Litigation Hold, has an Office 365 retention policy applied, or is placed on a hold associated with an eDiscovery case in the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="132f8-108">Dieser Inhalt wird zum Umschalten **Wiederherstellbare Elemente** Ordner in ihren Postfächern gespeichert.</span><span class="sxs-lookup"><span data-stu-id="132f8-108">This content is saved to participants' **Recoverable Items** folders in their mailboxes.</span></span>
  
<span data-ttu-id="132f8-109">Dateien, die in Postfächern in der Warteschleife beibehalten werden indiziert sind und können daher durchsucht werden, bei der Ausführung einer Inhaltssuche in das Wertpapier &amp; Compliance Center bei der Suche eines Teilnehmers Postfach.</span><span class="sxs-lookup"><span data-stu-id="132f8-109">Files that are retained in mailboxes on hold are indexed and can therefore be searched when running a Content Search in the Security &amp; Compliance Center when searching a participant's mailbox.</span></span> <span data-ttu-id="132f8-110">Allerdings angefügte Dateien, die größer als 39 MB sind mindestens zwei kleineren Dateien aufgeteilt werden und als komprimierte ZIP-Dateien gespeichert.</span><span class="sxs-lookup"><span data-stu-id="132f8-110">However, attached files that are larger than 39 MB are split into two or more smaller files and saved as compressed (.zip) files.</span></span> <span data-ttu-id="132f8-111">Der *Inhalt* dieser kleineren Dateien ist nicht für die Suche indiziert und möglicherweise nicht in einer Inhalts-Suche zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="132f8-111">The  *content*  of these smaller files is not indexed for search, and might not be returned in a Content Search.</span></span> <span data-ttu-id="132f8-112">Die *Metadaten* des diese Dateien (beispielsweise den Dateinamen und den Autor) wird für die Suche indiziert und möglicherweise in eine Inhaltssuche zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="132f8-112">However, the *metadata*  of these files (such as the file name and author) is indexed for search, and might be returned in a Content Search.</span></span>
  
> [!NOTE]
> <span data-ttu-id="132f8-113">Wenn das Postfach voll ist, oder den Administrator des Mandanten MaxSendSize konfiguriert um kleiner als 39 MB sein, hochgeladen Datei, die Daten nicht in allen aufbewahrt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="132f8-113">If the mailbox is full or the tenant admin has configured MaxSendSize to be smaller than 39 MB, uploaded file data will not be retained at all.</span></span> <span data-ttu-id="132f8-114">Der Standardwert MaxSendSize ist 150 MB, aber Mandanten-Admins können MaxSendSize liegend so klein wie 1 MB konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="132f8-114">The default MaxSendSize is 150 MB, but tenant admins can configure MaxSendSize to be as small as 1 MB.</span></span> 
  
<span data-ttu-id="132f8-115">Postfächer, die nicht in der Warteschleife sind haben keine Besprechungsdaten gespeichert.</span><span class="sxs-lookup"><span data-stu-id="132f8-115">Mailboxes that are not on hold will not have any meeting data saved.</span></span> <span data-ttu-id="132f8-116">Halten beispielsweise in einer Besprechung drei Personen in der die Postfächer der beiden Teilnehmer für die Beibehaltung markiert sind, auf die Postfächer von diese beiden Teilnehmer die Besprechungsdaten gespeichert werden, aber nicht an das Postfach von der dritte Teilnehmer, dessen Postfach nicht auf.</span><span class="sxs-lookup"><span data-stu-id="132f8-116">For example, in a three-person meeting in which the mailboxes of two participants are marked for retention, the meeting data is saved to the mailboxes of those two participants, but not to the mailbox of the third participant, whose mailbox is not on hold.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="132f8-117">See Also</span><span class="sxs-lookup"><span data-stu-id="132f8-117">Related topics</span></span>
[<span data-ttu-id="132f8-118">Erstellen von benutzerdefinierten externen Zugriffsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="132f8-118">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="132f8-119">Datenblöcke Point-Datei übertragen</span><span class="sxs-lookup"><span data-stu-id="132f8-119">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="132f8-120">Einrichten von Clientrichtlinien für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="132f8-120">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="132f8-121">Einrichten von konferenzrichtlinien in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="132f8-121">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)
  
## <a name="feedback"></a><span data-ttu-id="132f8-122">Feedback?</span><span class="sxs-lookup"><span data-stu-id="132f8-122">Feedback?</span></span>
<span data-ttu-id="132f8-123">Geben Sie Feedback zu Produkten oder uns Ihre Meinung kennen, finden Sie unter [Skype für Business Feedback](https://www.skypefeedback.com).</span><span class="sxs-lookup"><span data-stu-id="132f8-123">To provide product feedback or to let us know how we're doing, see [Skype for Business Feedback](https://www.skypefeedback.com).</span></span>