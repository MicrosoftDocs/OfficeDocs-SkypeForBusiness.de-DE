---
title: Erstellen von Benutzern, Hinzufügen von Microsoft 365 Business Voice-Lizenzen und Zuweisen von Telefonnummern
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: cb8277c11cbcc459da9da8fd8d4f5b9c329470f3
ms.sourcegitcommit: 9bead87a7f4c4e71f19f8980e9dce2b979735055
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2020
ms.locfileid: "41269281"
---
# <a name="create-and-license-business-voice-users-and-assign-them-phone-numbers"></a><span data-ttu-id="4263d-102">Erstellen und lizenzieren Sie Business Voice-Benutzer, und weisen Sie ihnen Telefonnummern zu</span><span class="sxs-lookup"><span data-stu-id="4263d-102">Create and license users and assign phone numbers to them</span></span>

<span data-ttu-id="4263d-103">Um :::no-loc text="Microsoft 365 Business Voice"::: zu verwenden, benötigen Sie ein :::no-loc text="Microsoft 365":::-Konto mit einer :::no-loc text="Microsoft 365 Business Voice with SMS"::: Lizenz.</span><span class="sxs-lookup"><span data-stu-id="4263d-103">To use :::no-loc text="Microsoft 365 Business Voice":::, you need a :::no-loc text="Microsoft 365"::: account that has a :::no-loc text="Microsoft 365 Business Voice with SMS"::: license.</span></span> <span data-ttu-id="4263d-104">Wenn Sie über ein Konto mit einer Lizenz verfügen, können Sie ihm eine Telefonnummer zuweisen.</span><span class="sxs-lookup"><span data-stu-id="4263d-104">When you have an account and license, you can assign a phone number to it.</span></span>

## <a name="create-and-license-users"></a><span data-ttu-id="4263d-105">Erstellen und Lizenzieren von Benutzern</span><span class="sxs-lookup"><span data-stu-id="4263d-105">Create and license users</span></span>

<span data-ttu-id="4263d-106">Führen Sie die Schritte in [Hinzufügen von Benutzern zu :::no-loc text="Office 365"::: einzeln oder in großen Mengen](https://docs.microsoft.com/office365/admin/add-users/add-users) aus.</span><span class="sxs-lookup"><span data-stu-id="4263d-106">Follow the steps in [Add users individually or in bulk to :::no-loc text="Office 365":::](https://docs.microsoft.com/office365/admin/add-users/add-users) to add one or more users.</span></span>

> [!NOTE]
> <span data-ttu-id="4263d-107">Wählen Sie im Bereich **Produktlizenzen zuweisen** die Option **:::no-loc text="Microsoft 365 Business Voice with SMS":::** aus.</span><span class="sxs-lookup"><span data-stu-id="4263d-107">In the **Assign product licenses** pane, be sure to select **:::no-loc text="Microsoft 365 Business Voice with SMS":::**.</span></span>

## <a name="assign-phone-numbers-to-users"></a><span data-ttu-id="4263d-108">Zuweisen von Telefonnummern an Benutzer</span><span class="sxs-lookup"><span data-stu-id="4263d-108">Assign phone numbers to users</span></span>

<span data-ttu-id="4263d-109">Nachdem Sie Benutzer erstellt und ihnen :::no-loc text="Microsoft 365 Business Voice with SMS":::-Lizenzen zugewiesen haben, können Sie ihnen Telefonnummern zuweisen.</span><span class="sxs-lookup"><span data-stu-id="4263d-109">After users have been created and assigned a :::no-loc text="Microsoft 365 Business Voice with SMS"::: license, you can assign phone numbers to them.</span></span> <span data-ttu-id="4263d-110">Sie benötigen eine noch nicht vergebene Telefonnummer für jeden Benutzer, der Anrufe an externe Telefonnummern tätigen oder von diesen empfangen muss.</span><span class="sxs-lookup"><span data-stu-id="4263d-110">You need one unassigned phone number for each user that needs to make or receive calls to or from external phone numbers.</span></span> <span data-ttu-id="4263d-111">Wenn Sie nicht über genügend nicht zugewiesene Telefonnummern verfügen, lesen Sie [Anfordern weiterer Telefonnummern](#get-more-phone-numbers) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="4263d-111">If you don't have enough unassigned phone numbers, see [Get more phone numbers](#get-more-phone-numbers) later in this article.</span></span>

1. <span data-ttu-id="4263d-112">Navigieren Sie in das Verzeichnis https://admin.teams.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="4263d-112">Go to https://admin.teams.microsoft.com</span></span>
2. <span data-ttu-id="4263d-113">Geben Sie einen Namen und eine Beschreibung für die Anforderung einer Telefonnummer ein.</span><span class="sxs-lookup"><span data-stu-id="4263d-113">Enter a name and description for the phone number request</span></span>
3. <span data-ttu-id="4263d-114">Wählen Sie **Anruf** > **Telefonnummern** aus.</span><span class="sxs-lookup"><span data-stu-id="4263d-114">Select **Voice** > **Phone numbers**.</span></span>
4. <span data-ttu-id="4263d-115">Suchen Sie eine Telefonnummer aus, die Sie einem Benutzer zuweisen möchten, und wählen Sie **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="4263d-115">Select a phone number you want to assign to a user and select **Edit**</span></span>
5. <span data-ttu-id="4263d-116">Geben Sie im Bereich **Bearbeiten** den Namen des Benutzers, dem Sie die Nummer zuweisen möchten, in **Zugewiesen an** ein.</span><span class="sxs-lookup"><span data-stu-id="4263d-116">In the **Edit** panel, enter the name of the user you want to assign the number to in **Assigned to** and select Assign</span></span> <span data-ttu-id="4263d-117">Wählen Sie dann **Zuweisen** aus.</span><span class="sxs-lookup"><span data-stu-id="4263d-117">Then select **Assign**.</span></span>
6. <span data-ttu-id="4263d-118">Geben Sie in **Notfallstandort** den Standort ein, an dem sich der Benutzer befindet, und wählen Sie dann **Anwenden** aus.</span><span class="sxs-lookup"><span data-stu-id="4263d-118">In **Emergency location**, enter the location where the user is located, and then select **Apply**</span></span>

## <a name="get-more-phone-numbers"></a><span data-ttu-id="4263d-119">Anfordern weiterer Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="4263d-119">Get more phone numbers</span></span>

<span data-ttu-id="4263d-120">Wenn Sie nicht über genügend Telefonnummern verfügen, um Sie neuen Benutzern zuzuweisen, können Sie weitere erhalten.</span><span class="sxs-lookup"><span data-stu-id="4263d-120">If you don't have enough phone numbers to assign to new users, you can get more.</span></span> <span data-ttu-id="4263d-121">Es kann bis zu 24 Stunden dauern, bis die von Ihnen bestellten Nummern verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="4263d-121">It may take up to 24 hours for numbers that you order to become available.</span></span>

1. <span data-ttu-id="4263d-122">Navigieren Sie in das Verzeichnis https://admin.teams.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="4263d-122">Go to https://admin.teams.microsoft.com</span></span>
2. <span data-ttu-id="4263d-123">Geben Sie einen Namen und eine Beschreibung für die Anforderung einer Telefonnummer ein.</span><span class="sxs-lookup"><span data-stu-id="4263d-123">Enter a name and description for the phone number request</span></span>
3. <span data-ttu-id="4263d-124">Wählen Sie **Anruf** > **Telefonnummern** > **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="4263d-124">Select **Voice** > **Phone numbers** > **Add**.</span></span>
4. <span data-ttu-id="4263d-125">Wählen Sie das Land oder die Region für die Telefonnummer aus.</span><span class="sxs-lookup"><span data-stu-id="4263d-125">Choose the country or region where the phone number should be created</span></span>
5. <span data-ttu-id="4263d-126">Wählen Sie in **Nummerntyp** **Benutzer (Abonnent)** aus.</span><span class="sxs-lookup"><span data-stu-id="4263d-126">In **Number type**, select **User (subscriber)**</span></span>
6. <span data-ttu-id="4263d-127">Suchen Sie in **Standort** nach dem des Benutzers, und wählen Sie ihn aus.</span><span class="sxs-lookup"><span data-stu-id="4263d-127">In **Location**, search for the location of the user and select it.</span></span> <span data-ttu-id="4263d-128">Sie können auch **Standort hinzuzufügen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="4263d-128">You can also choose to **Add a location**.</span></span>
7. <span data-ttu-id="4263d-129">Wählen Sie eine Ortsvorwahl aus, geben Sie die Anzahl der benötigten Telefonnummern ein, und wählen Sie dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="4263d-129">Choose an area code, enter the number of phone numbers to get, and then click **Next**</span></span>
8. <span data-ttu-id="4263d-130">Warten Sie, bis die Telefonnummern reserviert sind, und sehen Sie sich dann die Nummern an, die Sie erhalten.</span><span class="sxs-lookup"><span data-stu-id="4263d-130">Wait for the phone numbers to be reserved, and then view the numbers that you get.</span></span> <span data-ttu-id="4263d-131">Wenn alles gut aussieht, wählen Sie **Bestellung aufgeben** und dann **Fertig stellen** aus.</span><span class="sxs-lookup"><span data-stu-id="4263d-131">If everything looks ok, select **Place order** and then **Finish**.</span></span>
