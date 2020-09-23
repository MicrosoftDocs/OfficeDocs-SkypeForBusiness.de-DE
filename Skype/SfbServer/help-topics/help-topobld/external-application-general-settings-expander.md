---
title: Allgemeine Einstellungen für externe Anwendungen – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
description: Befolgen Sie diese Anweisungen, um die Eigenschaften für einen vertrauenswürdigen Anwendungsserver zu bearbeiten, der bereits definiert wurde.
ms.openlocfilehash: 9a9ed62040724d08ebcd711551cd1ce6e831d683
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218136"
---
# <a name="external-application-general-settings-expander"></a><span data-ttu-id="d5b72-103">Allgemeine Einstellungen für externe Anwendungen – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="d5b72-103">External Application General Settings Expander</span></span>
 
<span data-ttu-id="d5b72-104">Befolgen Sie diese Anweisungen, um die Eigenschaften für einen vertrauenswürdigen Anwendungsserver zu bearbeiten, der bereits definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="d5b72-104">To edit the properties for a trusted application server that has already been defined, follow these instructions.</span></span>
  
<span data-ttu-id="d5b72-105">Zwei Abschnitte können geändert werden:</span><span class="sxs-lookup"><span data-stu-id="d5b72-105">There are two sections that you can modify:</span></span>
  
> <span data-ttu-id="d5b72-106">Allgemeine Einstellungen</span><span class="sxs-lookup"><span data-stu-id="d5b72-106">General settings</span></span>
> 
> <span data-ttu-id="d5b72-107">Einstellungen für nächsten Hop</span><span class="sxs-lookup"><span data-stu-id="d5b72-107">Next hop settings</span></span>
    
## <a name="general-settings"></a><span data-ttu-id="d5b72-108">Allgemeine Einstellungen</span><span class="sxs-lookup"><span data-stu-id="d5b72-108">General Settings</span></span>

<span data-ttu-id="d5b72-p101">Sie können den aktuellen FQDN (Fully Qualified Domain Name) für den Pool vertrauenswürdiger Anwendungsserver ändern. Bearbeiten Sie den vollqualifizierten Namen für den Pool. Der DNS-A-Eintrag (Host) muss für den neuen Eintrag vorhanden sein, ehe sich Clients oder Server mit dem Pool mit dem neuen Namen verbinden können.</span><span class="sxs-lookup"><span data-stu-id="d5b72-p101">You can modify the current fully qualified domain name (FQDN) for the trusted application server pool. Edit the name of the pool FQDN. The Domain Name System (DNS) host (A) records must exist for the new entry before clients or servers can connect to the new pool name.</span></span>
  
<span data-ttu-id="d5b72-p102">Wählen Sie **Replikation von Konfigurationsdaten in diesen Pool aktivieren** aus, wenn die Replikation von Konfigurationsdaten in diesen Pool erforderlich sein sollte. Deaktivieren Sie dieses Kontrollkästchen, wenn die Konfigurationsdaten nicht repliziert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d5b72-p102">Select **Enable replication of configuration data to this pool** if you need to have replication of configuration data to this pool. Clear the check mark if you do not want to replicate the configuration data.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="d5b72-114">Einstellungen für nächsten Hop</span><span class="sxs-lookup"><span data-stu-id="d5b72-114">Next Hop Settings</span></span>

<span data-ttu-id="d5b72-115">Sie können den Server für den nächsten Hop des vertrauenswürdigen Anwendungsserver Pools angeben, indem Sie den definierten Enterprise Edition-Front-End-Pool oder Standard Edition-Front-End-Server aus der Dropdownliste auswählen.</span><span class="sxs-lookup"><span data-stu-id="d5b72-115">You can specify the trusted application server pool's next hop server by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="d5b72-116">Ein Director oder Director-Pool kann nicht als nächster Hop für einen vertrauenswürdigen Anwendungsserver ausgewählt werden und wird daher nicht in der Liste aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="d5b72-116">A Director or Director pool is not a valid selection for a trusted application server next hop and will not appear in the list.</span></span>
  


<span data-ttu-id="d5b72-117">Klicken Sie auf **OK** , um die Änderungen zu akzeptieren und zu speichern.</span><span class="sxs-lookup"><span data-stu-id="d5b72-117">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="d5b72-118">Klicken Sie auf **Abbrechen**, um Ihre Änderungen zu verwerfen und die Eigenschaftenseite zu schließen.</span><span class="sxs-lookup"><span data-stu-id="d5b72-118">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  

