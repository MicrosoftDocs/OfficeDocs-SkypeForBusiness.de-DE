---
title: Einstellungen für den Front-End-Vermittlungsdienst für Lync Server 2010 – Erweiterung
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
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: 'In diesem Dialogfeld bearbeiten Sie die Eigenschaften der Einstellungen unter PSTN-Gateway für Vermittlungsserver. Sie können die folgenden Einstellungen definieren:'
ms.openlocfilehash: 37baf89b6100528c1485f939f69e20c697803123
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217726"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a><span data-ttu-id="fd630-104">Einstellungen für den Front-End-Vermittlungsdienst für Lync Server 2010 – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="fd630-104">Front End Mediation Service Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="fd630-105">In diesem Dialogfeld bearbeiten Sie die Eigenschaften der Einstellungen unter **PSTN-Gateway für Vermittlungsserver**.</span><span class="sxs-lookup"><span data-stu-id="fd630-105">You edit the properties of the **Mediation Server PSTN gateway** settings in this dialog.</span></span> <span data-ttu-id="fd630-106">Sie können die folgenden Einstellungen definieren:</span><span class="sxs-lookup"><span data-stu-id="fd630-106">You define the following settings:</span></span>
  
- <span data-ttu-id="fd630-107">Wählen Sie den verbundenen **Vermittlungsserver aktiviert** aus, wenn Sie den Vermittlungsserver mit diesem Front-End-Server-oder Front-End-Pool collocate möchten.</span><span class="sxs-lookup"><span data-stu-id="fd630-107">Select the **Collocated Mediation Server enabled** if you want to collocate the Mediation Server with this Front End Server or Front End pools.</span></span>
    
- <span data-ttu-id="fd630-108">**Abhör Anschlüsse**: definieren Sie die Ports, auf denen die Vermittlungsserver überwacht werden soll.</span><span class="sxs-lookup"><span data-stu-id="fd630-108">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="fd630-109">Sie können einen Port für **TLS** (Transport Layer Security) oder **TCP** (Transport Control Protocol) definieren.</span><span class="sxs-lookup"><span data-stu-id="fd630-109">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="fd630-110">Damit der Porteintrag für TCP verfügbar ist, müssen Sie das Kontrollkästchen **TCP-Port aktivieren** aktivieren.</span><span class="sxs-lookup"><span data-stu-id="fd630-110">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="fd630-111">Ermitteln Sie anhand der Dokumentation und Konfigurationseinstellungen für das PSTN-Gateway (Public Switched Telephone Network), ob Sie Portwerte für TLS, TCP oder beides aktivieren und definieren müssen.</span><span class="sxs-lookup"><span data-stu-id="fd630-111">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="fd630-112">TLS ist ein sichereres Protokoll, das Zertifikate verwendet, um den Datenverkehr zwischen dem Vermittlungsserver und dem PSTN-Gateway zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="fd630-112">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="fd630-113">Nicht alle PSTN-Gateways unterstützen TLS.</span><span class="sxs-lookup"><span data-stu-id="fd630-113">Not all PSTN gateways support TLS.</span></span> 
  
- <span data-ttu-id="fd630-114">Auflistung des momentan zugeordneten und vorhandenen **Trunks** (Session Initiation Protocol-Trunks (SIP)), **Gateways** (PSTN-Gateway oder IP-PBX) und **Standorts** (für Trunk und Gateway konfigurierter Standort).</span><span class="sxs-lookup"><span data-stu-id="fd630-114">A listing of currently associated and existing **Trunk** (that is, Session Initiation Protocol (SIP) Trunks), **Gateway** (PSTN gateway or IP-PBX) and **Site** (configured site for the trunk and gateway).</span></span>
    
- <span data-ttu-id="fd630-p105">Wählen Sie einen Trunk, ein Gateway und einen Standort aus, und klicken Sie auf **Als Standardeinstellung festlegen**, um die Auswahl als Standardeinstellung für diesen Vermittlungsdienst festzulegen. Um die Auswahl als Standardeinstellung aufzuheben, wählen Sie die aktuelle Standardeinstellung aus und klicken auf **Festlegung als Standardeinstellung aufheben**. Wählen Sie anschließend eine neue Standardeinstellung aus, und klicken Sie auf **Als Standardeinstellung festlegen**.</span><span class="sxs-lookup"><span data-stu-id="fd630-p105">You select a Trunk, Gateway and Site and click **Make Default** to set the selection as the default for this Mediation service. You select the current default and click **Unmake Default** to remove the selection as the current default. You then select a new default and click **Make Default**.</span></span>
    
  <span data-ttu-id="fd630-118">**OK**: Mit dieser Option werden die Änderungen am Dialogfeld akzeptiert und übernommen.</span><span class="sxs-lookup"><span data-stu-id="fd630-118">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="fd630-119">**Abbrechen**: Mit dieser Option werden die Änderungen verworfen, und das Dialogfeld wird geschlossen.</span><span class="sxs-lookup"><span data-stu-id="fd630-119">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="fd630-120">**Hilfe**: Mit dieser Option zeigen Sie diese Hilfeseite an.</span><span class="sxs-lookup"><span data-stu-id="fd630-120">**Help** Displays this help screen.</span></span>
  

