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
- NOCSH
ms.custom:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
description: Führen Sie die folgenden Anweisungen aus, um die Eigenschaften für einen vertrauenswürdigen Anwendungsserver zu bearbeiten, der bereits definiert wurde.
ms.openlocfilehash: be3a1318608f1e82119bf21580b7d155bd4b360b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819987"
---
# <a name="external-application-general-settings-expander"></a><span data-ttu-id="a4417-103">Allgemeine Einstellungen für externe Anwendungen – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="a4417-103">External Application General Settings Expander</span></span>
 
<span data-ttu-id="a4417-104">Führen Sie die folgenden Anweisungen aus, um die Eigenschaften für einen vertrauenswürdigen Anwendungsserver zu bearbeiten, der bereits definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="a4417-104">To edit the properties for a trusted application server that has already been defined, follow these instructions.</span></span>
  
<span data-ttu-id="a4417-105">Es gibt zwei Abschnitte, die Sie ändern können:</span><span class="sxs-lookup"><span data-stu-id="a4417-105">There are two sections that you can modify:</span></span>
  
> <span data-ttu-id="a4417-106">Allgemeine Einstellungen</span><span class="sxs-lookup"><span data-stu-id="a4417-106">General settings</span></span>
> 
> <span data-ttu-id="a4417-107">Einstellungen für nächsten Hop</span><span class="sxs-lookup"><span data-stu-id="a4417-107">Next hop settings</span></span>
    
## <a name="general-settings"></a><span data-ttu-id="a4417-108">Allgemeine Einstellungen</span><span class="sxs-lookup"><span data-stu-id="a4417-108">General Settings</span></span>

<span data-ttu-id="a4417-109">Sie können den aktuellen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für den vertrauenswürdigen Anwendungsserver Pool ändern.</span><span class="sxs-lookup"><span data-stu-id="a4417-109">You can modify the current fully qualified domain name (FQDN) for the trusted application server pool.</span></span> <span data-ttu-id="a4417-110">Bearbeiten Sie den Namen des FQDN des Pools.</span><span class="sxs-lookup"><span data-stu-id="a4417-110">Edit the name of the pool FQDN.</span></span> <span data-ttu-id="a4417-111">Für den neuen Eintrag müssen die DNS-Host (A)-Einträge (Domain Name System) vorhanden sein, bevor Clients oder Server eine Verbindung mit dem neuen Pool Namen herstellen können.</span><span class="sxs-lookup"><span data-stu-id="a4417-111">The Domain Name System (DNS) host (A) records must exist for the new entry before clients or servers can connect to the new pool name.</span></span>
  
<span data-ttu-id="a4417-112">Wählen Sie **Replikation von Konfigurationsdaten in diesem Pool aktivieren** aus, wenn Sie die Replikation von Konfigurationsdaten in diesen Pool benötigen.</span><span class="sxs-lookup"><span data-stu-id="a4417-112">Select **Enable replication of configuration data to this pool** if you need to have replication of configuration data to this pool.</span></span> <span data-ttu-id="a4417-113">Deaktivieren Sie das Häkchen, wenn Sie die Konfigurationsdaten nicht replizieren möchten.</span><span class="sxs-lookup"><span data-stu-id="a4417-113">Clear the check mark if you do not want to replicate the configuration data.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="a4417-114">Einstellungen für den nächsten Hop</span><span class="sxs-lookup"><span data-stu-id="a4417-114">Next Hop Settings</span></span>

<span data-ttu-id="a4417-115">Sie können den nächsten Hop-Server des Trusted Application Server-Pools angeben, indem Sie den definierten Enterprise Edition-Front-End-Pool oder den Standard Edition-Front-End-Server aus der Dropdownliste auswählen.</span><span class="sxs-lookup"><span data-stu-id="a4417-115">You can specify the trusted application server pool's next hop server by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="a4417-116">Ein Director-oder Director-Pool ist keine gültige Auswahl für einen Trusted Application Server-nächsten Hop und wird nicht in der Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a4417-116">A Director or Director pool is not a valid selection for a trusted application server next hop and will not appear in the list.</span></span>
  


<span data-ttu-id="a4417-117">Klicken Sie auf **OK** , um die Änderungen zu übernehmen und zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a4417-117">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="a4417-118">Klicken Sie auf **Abbrechen**, um Ihre Änderungen zu verwerfen und die Eigenschaftenseite zu schließen.</span><span class="sxs-lookup"><span data-stu-id="a4417-118">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  

