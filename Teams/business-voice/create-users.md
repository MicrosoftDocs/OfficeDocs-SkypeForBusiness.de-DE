---
title: Erstellen von Benutzern, Hinzufügen von Microsoft 365 Business Voice-Lizenzen und Zuweisen von Telefonnummern
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
ms.openlocfilehash: 851c661a2a75a3dfe82212b896041ddd2516c678
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824833"
---
# <a name="create-and-license-business-voice-users-and-assign-them-phone-numbers"></a><span data-ttu-id="5efb9-102">Erstellen und lizenzieren Sie Business Voice-Benutzer, und weisen Sie ihnen Telefonnummern zu</span><span class="sxs-lookup"><span data-stu-id="5efb9-102">Create and license Business Voice users and assign them phone numbers</span></span>

<span data-ttu-id="5efb9-103">Um :::no-loc text="Microsoft 365 Business Voice"::: zu verwenden, benötigen Sie ein :::no-loc text="Microsoft 365":::-Konto mit einer :::no-loc text="Microsoft 365 Business Voice with SMS"::: Lizenz.</span><span class="sxs-lookup"><span data-stu-id="5efb9-103">To use :::no-loc text="Microsoft 365 Business Voice":::, you need a :::no-loc text="Microsoft 365"::: account that has a :::no-loc text="Microsoft 365 Business Voice with SMS"::: license.</span></span> <span data-ttu-id="5efb9-104">Wenn Sie über ein Konto mit einer Lizenz verfügen, können Sie ihm eine Telefonnummer zuweisen.</span><span class="sxs-lookup"><span data-stu-id="5efb9-104">When you have an account and license, you can assign a phone number to it.</span></span>

## <a name="create-and-license-users"></a><span data-ttu-id="5efb9-105">Erstellen und Lizenzieren von Benutzern</span><span class="sxs-lookup"><span data-stu-id="5efb9-105">Create and license users</span></span>

<span data-ttu-id="5efb9-106">Führen Sie die Schritte in [Hinzufügen von Benutzern zu :::no-loc text="Office 365"::: einzeln oder in großen Mengen](https://docs.microsoft.com/office365/admin/add-users/add-users) aus.</span><span class="sxs-lookup"><span data-stu-id="5efb9-106">Follow the steps in [Add users individually or in bulk to :::no-loc text="Office 365":::](https://docs.microsoft.com/office365/admin/add-users/add-users).</span></span>

> [!NOTE]
> <span data-ttu-id="5efb9-107">Wählen Sie im Bereich **Produktlizenzen zuweisen** die Option **:::no-loc text="Microsoft 365 Business Voice with SMS":::** aus.</span><span class="sxs-lookup"><span data-stu-id="5efb9-107">In the **Assign product licenses** pane,  select **:::no-loc text="Microsoft 365 Business Voice with SMS":::**.</span></span>

## <a name="assign-phone-numbers-to-users"></a><span data-ttu-id="5efb9-108">Zuweisen von Telefonnummern an Benutzer</span><span class="sxs-lookup"><span data-stu-id="5efb9-108">Assign phone numbers to users</span></span>

<span data-ttu-id="5efb9-109">Nachdem Sie Benutzer erstellt und ihnen :::no-loc text="Microsoft 365 Business Voice with SMS":::-Lizenzen zugewiesen haben, können Sie ihnen Telefonnummern zuweisen.</span><span class="sxs-lookup"><span data-stu-id="5efb9-109">After you create users and assigned them a :::no-loc text="Microsoft 365 Business Voice with SMS"::: license, you can assign phone numbers to them.</span></span> <span data-ttu-id="5efb9-110">Sie benötigen eine noch nicht vergebene Telefonnummer für jeden Benutzer, der Anrufe an externe Telefonnummern tätigen oder von diesen empfangen muss.</span><span class="sxs-lookup"><span data-stu-id="5efb9-110">You need one unassigned phone number for each user that needs to make or receive calls to or from external phone numbers.</span></span> <span data-ttu-id="5efb9-111">Wenn Sie nicht über genügend nicht zugewiesene Telefonnummern verfügen, lesen Sie [Anfordern weiterer Telefonnummern](#get-more-phone-numbers) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="5efb9-111">If you don't have enough unassigned phone numbers, see [Get more phone numbers](#get-more-phone-numbers) later in this article.</span></span>

1. <span data-ttu-id="5efb9-112">Navigieren Sie in das Verzeichnis https://admin.teams.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="5efb9-112">Go to https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="5efb9-113">Geben Sie einen Namen und eine Beschreibung für die Anforderung einer Telefonnummer ein.</span><span class="sxs-lookup"><span data-stu-id="5efb9-113">Enter a name and description for the phone number request.</span></span>
3. <span data-ttu-id="5efb9-114">Wählen Sie **Anruf** > **Telefonnummern** aus.</span><span class="sxs-lookup"><span data-stu-id="5efb9-114">Select **Voice** > **Phone numbers**.</span></span>
4. <span data-ttu-id="5efb9-115">Suchen Sie eine Telefonnummer aus, die Sie einem Benutzer zuweisen möchten, und wählen Sie **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="5efb9-115">Select a phone number that you want to assign to a user, and then select **Edit**.</span></span>
5. <span data-ttu-id="5efb9-116">Geben Sie im Bereich **Bearbeiten** den Namen des Benutzers, dem Sie die Nummer zuweisen möchten, in **Zugewiesen an** ein.</span><span class="sxs-lookup"><span data-stu-id="5efb9-116">In the **Edit** panel, enter the name of the user that you want to assign the number to in **Assigned to**.</span></span> <span data-ttu-id="5efb9-117">Wählen Sie dann **Zuweisen** aus.</span><span class="sxs-lookup"><span data-stu-id="5efb9-117">Then select **Assign**.</span></span>
6. <span data-ttu-id="5efb9-118">Geben Sie in **Notfallstandort** den Standort ein, an dem sich der Benutzer befindet, und wählen Sie dann **Anwenden** aus.</span><span class="sxs-lookup"><span data-stu-id="5efb9-118">For **Emergency location**, enter the location where the user is located, and then select **Apply**</span></span>

## <a name="get-more-phone-numbers"></a><span data-ttu-id="5efb9-119">Anfordern weiterer Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="5efb9-119">Get more phone numbers</span></span>

<span data-ttu-id="5efb9-120">Wenn Sie nicht über genügend Telefonnummern verfügen, um Sie neuen Benutzern zuzuweisen, können Sie weitere erhalten.</span><span class="sxs-lookup"><span data-stu-id="5efb9-120">If you don't have enough phone numbers to assign to new users, you can get more.</span></span> <span data-ttu-id="5efb9-121">Es kann bis zu 24 Stunden dauern, bis die von Ihnen bestellten Nummern verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="5efb9-121">It may take up to 24 hours for numbers that you order to become available.</span></span>

1. <span data-ttu-id="5efb9-122">Navigieren Sie in das Verzeichnis https://admin.teams.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="5efb9-122">Go to https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="5efb9-123">Geben Sie einen Namen und eine Beschreibung für die Anforderung einer Telefonnummer ein.</span><span class="sxs-lookup"><span data-stu-id="5efb9-123">Enter a name and description for the phone number request.</span></span>
3. <span data-ttu-id="5efb9-124">Wählen Sie **Anruf** > **Telefonnummern** > **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="5efb9-124">Select **Voice** > **Phone numbers** > **Add**.</span></span>
4. <span data-ttu-id="5efb9-125">Wählen Sie das Land oder die Region für die Telefonnummer aus.</span><span class="sxs-lookup"><span data-stu-id="5efb9-125">Choose the country or region for the phone number.</span></span>
5. <span data-ttu-id="5efb9-126">Wählen Sie in **Nummerntyp** **Benutzer (Abonnent)** aus.</span><span class="sxs-lookup"><span data-stu-id="5efb9-126">For **Number type**, select **User (subscriber)**.</span></span>
6. <span data-ttu-id="5efb9-127">Suchen Sie in **Standort** nach dem des Benutzers, und wählen Sie ihn aus.</span><span class="sxs-lookup"><span data-stu-id="5efb9-127">For **Location**, search for the location of the user and select it.</span></span> <span data-ttu-id="5efb9-128">Sie können auch **Standort hinzuzufügen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="5efb9-128">You can also choose to **Add a location**.</span></span>
7. <span data-ttu-id="5efb9-129">Wählen Sie eine Ortsvorwahl aus, geben Sie die Anzahl der benötigten Telefonnummern ein, und wählen Sie dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="5efb9-129">Choose an area code, enter the number of phone numbers that you need, and then select **Next**.</span></span>
8. <span data-ttu-id="5efb9-130">Warten Sie, bis die Telefonnummern reserviert sind, und sehen Sie sich dann die Nummern an, die Sie erhalten.</span><span class="sxs-lookup"><span data-stu-id="5efb9-130">Wait for the phone numbers to be reserved, and then view the numbers that you get.</span></span> <span data-ttu-id="5efb9-131">Wenn alles gut aussieht, wählen Sie **Bestellung aufgeben** und dann **Fertig stellen** aus.</span><span class="sxs-lookup"><span data-stu-id="5efb9-131">If everything looks ok, select **Place order** and then **Finish**.</span></span>
