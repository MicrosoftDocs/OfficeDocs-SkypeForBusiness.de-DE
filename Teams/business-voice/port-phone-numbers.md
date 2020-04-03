---
title: Portieren von Telefonnummern in Business Voice
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1dab1673f32c6a3c902c761004e5720d8c61dbfb
ms.sourcegitcommit: 4ee9835282e1440d03abc6dbcd172bc20c5b3015
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2020
ms.locfileid: "43096890"
---
# <a name="move-port-phone-numbers-to-business-voice"></a><span data-ttu-id="8a159-102">Übertragen (Portieren) von Telefonnummern in Business Voice</span><span class="sxs-lookup"><span data-stu-id="8a159-102">Move (port) phone numbers to Business Voice</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8a159-103">Die Informationen in diesem Artikel gelten nur für Business Voice **mit** Anrufplan.</span><span class="sxs-lookup"><span data-stu-id="8a159-103">The information in this article is applicable to Business Voice **with** Calling Plan only.</span></span> <span data-ttu-id="8a159-104">Business Voice mit Anrufplan steht nur in ausgewählten Ländern und Regionen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="8a159-104">Business Voice with Calling Plan is available only in select countries and regions.</span></span> <span data-ttu-id="8a159-105">Bevor Sie diesen Artikel lesen, schauen Sie unter [Regionale Verfügbarkeit für Business Voice](country-region-availability.md), nach, ob Ihr Land oder Ihre Region Business Voice mit Anrufplan unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8a159-105">Before reading this article, check [Country and region availability for Business Voice](country-region-availability.md) to see whether your country or region supports Business Voice with Calling Plan.</span></span>
>
> <span data-ttu-id="8a159-106">Wenn sich Ihr Mandant in einem Land oder einer Region befindet, das bzw. die Business Voice mit Anrufplan nicht unterstützt, ziehen Sie [Hilfe von einem Microsoft-Vertriebspartner oder Partner erhalten](reseller-partner-support.md) zurate.</span><span class="sxs-lookup"><span data-stu-id="8a159-106">If your tenant is located in a country or region that doesn't support Business Voice with Calling Plan, check out [Get help from a Microsoft reseller or partner](reseller-partner-support.md).</span></span>

<span data-ttu-id="8a159-107">Wenn der Assistent für erste Schritte Ihnen bei der Einrichtung von Business Voice hilft, weist er Telefonnummern für die Haupttelefonleitung des Unternehmens sowie für alle Benutzer zu, denen Sie eine Business Voice-Lizenz zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="8a159-107">When the Getting Started wizard helps you set up Business Voice, it assigns phone numbers for the main company line and for any users that you've assigned a Business Voice license to.</span></span> <span data-ttu-id="8a159-108">Wenn Sie bereits über Telefonnummern verfügen, die Sie beim Umstellen auf Business Voice beibehalten möchten, können Sie diese mithilfe eines Verfahrens, das Portieren von Telefonnummern genannt wird, in Business Voice übertragen.</span><span class="sxs-lookup"><span data-stu-id="8a159-108">If you already have phone numbers that you want to keep when you move to Business Voice, you can bring them with you by using a process called phone number porting to bring them over to Business Voice.</span></span> <span data-ttu-id="8a159-109">Nachdem Sie Ihre Telefonnummern in Business Voice portiert haben, weisen Sie sie Benutzern und Diensten zu.</span><span class="sxs-lookup"><span data-stu-id="8a159-109">After you port your phone numbers to Business Voice, you assign them to users and services.</span></span> <span data-ttu-id="8a159-110">Die alten Nummern ersetzen die temporären Nummern, die vom Assistenten für erste Schritte zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="8a159-110">The old numbers replace the temporary numbers that the Getting Started wizard assigned.</span></span>

<span data-ttu-id="8a159-111">Bevor Sie Nummern in Business Voice verschieben, sehen Sie sich [Häufige Fragen zum Übertragen von Telefonnummern](../transferring-phone-numbers-common-questions.md) an.</span><span class="sxs-lookup"><span data-stu-id="8a159-111">Before you move numbers to Business Voice, take a look at [Transferring phone numbers common questions](../transferring-phone-numbers-common-questions.md).</span></span> <span data-ttu-id="8a159-112">Dieser Artikel umfasst Antworten auf Fragen wie z. B. welche Länder oder Regionen unterstützt werden, welche Nummern nicht übertragen werden können, welche Informationen Sie benötigen, usw.</span><span class="sxs-lookup"><span data-stu-id="8a159-112">This article includes answers to questions including what countries and regions are supported, what numbers can and can't be transferred, and what information you'll need.</span></span>

<span data-ttu-id="8a159-113">Wenn Sie bereit sind, Ihre Telefonnummern in Business Voice zu verschieben, führen Sie die Schritte unter [Übertragen von Telefonnummern in Office 365](../transfer-phone-numbers-to-office-365.md) aus, um einen Portierungsauftrag zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8a159-113">When you're ready to move your phone numbers to Business Voice, follow the steps in [Transfer phone numbers to Office 365](../transfer-phone-numbers-to-office-365.md) to create a port order.</span></span> <span data-ttu-id="8a159-114">Ein Portierungsauftrag umfasst alle Informationen, die nötig sind, um Ihre Nummern von Ihrem aktuellen Telefondienstanbieter in Business Voice zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="8a159-114">The order includes the information that's needed to move your numbers from your current phone service carrier to Business Voice.</span></span>

<span data-ttu-id="8a159-115">Nachdem Ihre Telefonnummern in Business Voice verschoben wurden, müssen Sie sie Personen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="8a159-115">After your phone numbers have been moved to Business Voice, you need to assign them to people.</span></span> <span data-ttu-id="8a159-116">Führen Sie dazu die Schritte in [Ändern einer Telefonnummer für einen Benutzer](../assign-change-or-remove-a-phone-number-for-a-user.md#change-a-phone-number-for-a-user) aus.</span><span class="sxs-lookup"><span data-stu-id="8a159-116">To do that, follow the steps in [Change a phone number for a user](../assign-change-or-remove-a-phone-number-for-a-user.md#change-a-phone-number-for-a-user).</span></span> <span data-ttu-id="8a159-117">Wenn Sie diese Schritte ausführen, ersetzen Sie die Telefonnummer, die dem Benutzer vorübergehend zugewiesen wurde, durch die ursprüngliche, von Ihnen portierte Telefonnummer.</span><span class="sxs-lookup"><span data-stu-id="8a159-117">When you follow these steps, you'll replace the phone number that was temporarily assigned to the user with their original phone number that you ported over.</span></span>

<span data-ttu-id="8a159-118">Wenn Sie Hilfe benötigen, teilen Sie uns dies mit.</span><span class="sxs-lookup"><span data-stu-id="8a159-118">If you need help, let us know!</span></span> <span data-ttu-id="8a159-119">Wir möchten Ihnen helfen, Ihre Telefonnummern so einfach wie möglich in Business Voice zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="8a159-119">We're here to help you get your phone numbers moved to Business Voice as easy as possible.</span></span> <span data-ttu-id="8a159-120">Achten Sie darauf, folgende Informationen anzugeben:</span><span class="sxs-lookup"><span data-stu-id="8a159-120">Be sure to include the following information:</span></span>
- <span data-ttu-id="8a159-121">Ihre Organisations-ID (z. B. ***Contoso***.onmicrosoft.com)</span><span class="sxs-lookup"><span data-stu-id="8a159-121">Your organization ID (such as ***contoso***.onmicrosoft.com)</span></span>
- <span data-ttu-id="8a159-122">Bei welchen Typen und wie vielen Nummern Sie Hilfe benötigen</span><span class="sxs-lookup"><span data-stu-id="8a159-122">What types and how many numbers you need help with</span></span>
- <span data-ttu-id="8a159-123">Die autorisierende Person Ihres Kontos</span><span class="sxs-lookup"><span data-stu-id="8a159-123">The authorizing person on your account</span></span>
- <span data-ttu-id="8a159-124">Eine Beschreibung des Problems oder der Frage, die Sie haben.</span><span class="sxs-lookup"><span data-stu-id="8a159-124">A description of the issue or question that you have</span></span>

<span data-ttu-id="8a159-125">Wenn Sie Hilfe zu Telefonnummern in Kanada und den Vereinigten Staaten wünschen, senden Sie Ihre Anfrage an [ptn@microsoft.com](mailto:ptn@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="8a159-125">For help with phone numbers in Canada and the United States, send your request to [ptn@microsoft.com](mailto:ptn@microsoft.com).</span></span>

<span data-ttu-id="8a159-126">Wenn Sie Hilfe zu Telefonnummern in Europa wünschen, senden Sie Ihre Anfrage an [ptneu@microsoft.com](mailto:ptneu@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="8a159-126">For help with phone numbers in Europe, send your request to [ptneu@microsoft.com](mailto:ptneu@microsoft.com).</span></span>
