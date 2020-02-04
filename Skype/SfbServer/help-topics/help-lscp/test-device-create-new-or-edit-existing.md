---
title: Test Gerät neues erstellen oder vorhandenes bearbeiten
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ClientDeviceTestEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f9125dd-04b3-4a6d-9f41-4f19ddaf7a2d
description: Die Funktion „Testgerät“ wird zusammen mit der Funktion „Geräteaktualisierung“ verwendet. Sie können der Seite Testgerät ein Gerät hinzufügen und mit diesem Gerät anschließend die Funktionalität neuer Updates überprüfen, bevor die Updates auf Produktionsgeräten bereitgestellt werden. Sie können ein Gerät global (innerhalb Ihrer gesamten Umgebung) oder innerhalb eines einzelnen Standorts testen. Sie identifizieren ein Testgerät über seine MAC-Adresse (Media Access Control) oder Seriennummer. Wenn Sie ein Gerät hinzufügen, wird es in der Liste auf der Seite Testgerät des Skype for Business Server-Control Panels angezeigt.
ms.openlocfilehash: 56f5c7b43f55f50c5fa5e73cade3f74bea752778
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41699464"
---
# <a name="test-device-create-new-or-edit-existing"></a><span data-ttu-id="712fc-107">Testgerät: Erstellen eines neuen oder Bearbeiten eines vorhandenen Testgeräts</span><span class="sxs-lookup"><span data-stu-id="712fc-107">Test Device: Create New or Edit Existing</span></span>

<span data-ttu-id="712fc-108">Die Funktion „Testgerät“ wird zusammen mit der Funktion „Geräteaktualisierung“ verwendet.</span><span class="sxs-lookup"><span data-stu-id="712fc-108">The Test Device feature works in conjunction with the Device Update feature.</span></span> <span data-ttu-id="712fc-109">Sie können der Seite **Testgerät** ein Gerät hinzufügen und mit diesem Gerät anschließend die Funktionalität neuer Updates überprüfen, bevor die Updates auf Produktionsgeräten bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="712fc-109">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="712fc-110">Sie können ein Gerät global (innerhalb Ihrer gesamten Umgebung) oder innerhalb eines einzelnen Standorts testen.</span><span class="sxs-lookup"><span data-stu-id="712fc-110">You can test a device globally (throughout your entire environment) or within a single site.</span></span> <span data-ttu-id="712fc-111">Sie identifizieren ein Testgerät über seine MAC-Adresse (Media Access Control) oder Seriennummer.</span><span class="sxs-lookup"><span data-stu-id="712fc-111">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="712fc-112">Wenn Sie ein Gerät hinzufügen, wird es in der Liste auf der Seite **Testgerät** des Skype for Business Server-Control Panels angezeigt.</span><span class="sxs-lookup"><span data-stu-id="712fc-112">When you add a device, it appears in the list on the **Test Device** page of the Skype for Business Server Control Panel.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="712fc-113">Mögliche Aufgaben</span><span class="sxs-lookup"><span data-stu-id="712fc-113">Tasks you can perform</span></span>

<span data-ttu-id="712fc-114">Auf der Seite **Neues Testgerät** bzw. **Testgerät bearbeiten** können Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="712fc-114">You can perform the following tasks on the **New Test Device** or **Edit Test Device** page:</span></span>

- <span data-ttu-id="712fc-115">Hinzufügen eines neuen Testgeräts</span><span class="sxs-lookup"><span data-stu-id="712fc-115">Add a new test device.</span></span>

- <span data-ttu-id="712fc-116">Ändern der Eigenschaften eines vorhandenen Testgeräts</span><span class="sxs-lookup"><span data-stu-id="712fc-116">Modify the properties of an existing test device.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="712fc-117">Referenz zur Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="712fc-117">UI Reference</span></span>

<span data-ttu-id="712fc-118">In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="712fc-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="712fc-119">**Bereich** Identifiziert den Bereich (Global oder Website) des Testgeräts.</span><span class="sxs-lookup"><span data-stu-id="712fc-119">**Scope** Identifies the scope (Global or Site) of the test device.</span></span>

- <span data-ttu-id="712fc-120">**Name** Sie können den Namen des Testgeräts hinzufügen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="712fc-120">**Name** You can add or modify the name of the test device.</span></span>

- <span data-ttu-id="712fc-121">**Gerätename** Sie können den Namen des Testgeräts hinzufügen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="712fc-121">**Device name** You can add or modify the name of the test device.</span></span>

- <span data-ttu-id="712fc-122">**Identifier-Typ** Sie können die zum Identifizieren des Geräts zu verwendende Methode auswählen, indem Sie eine der folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="712fc-122">**Identifier type** You can select the method to use to identify the device by selecting one of the following:</span></span>

  - <span data-ttu-id="712fc-123">**MAC-Adresse**</span><span class="sxs-lookup"><span data-stu-id="712fc-123">**MAC address**</span></span>

  - <span data-ttu-id="712fc-124">**Seriennummer**</span><span class="sxs-lookup"><span data-stu-id="712fc-124">**Serial number**</span></span>

- <span data-ttu-id="712fc-125">**Eindeutiger Bezeichner** Sie können die Mac-Adresse oder die Seriennummer des Geräts eingeben.</span><span class="sxs-lookup"><span data-stu-id="712fc-125">**Unique identifier** You can type the MAC address or serial number of the device.</span></span>

<span data-ttu-id="712fc-126">Ausführliche Informationen zu Testgeräten finden Sie unter [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="712fc-126">For details about testing devices, see [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) in the Operations documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="712fc-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="712fc-127">See also</span></span>

[<span data-ttu-id="712fc-128">Testgerät</span><span class="sxs-lookup"><span data-stu-id="712fc-128">Test Device</span></span>](test-device.md)

[<span data-ttu-id="712fc-129">Neu – CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="712fc-129">New-CsTestDevice</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)

[<span data-ttu-id="712fc-130">Satz-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="712fc-130">Set-CsTestDevice</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)

[<span data-ttu-id="712fc-131">Anzeigen von Software Updates für Geräte in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="712fc-131">View Software Updates for Devices in Your Organization</span></span>](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)
