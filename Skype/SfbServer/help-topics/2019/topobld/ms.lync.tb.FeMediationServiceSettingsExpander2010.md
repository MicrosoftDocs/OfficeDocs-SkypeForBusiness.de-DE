---
title: Front-End Mediation Service Einstellungen – Erweiterung für Lync Server 2010
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: 'Sie können die Eigenschaften der Mediation Server PSTN-gatewayeinstellungen in diesem Dialogfeld bearbeiten. Definieren Sie die folgenden Einstellungen:'
ms.openlocfilehash: 7343fb4e2876ffa23fa7d37a8669f9b0c25f428b
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/20/2018
ms.locfileid: "19979771"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a><span data-ttu-id="c61c5-104">Front-End Mediation Service Einstellungen – Erweiterung für Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="c61c5-104">Front End Mediation Service Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="c61c5-105">Sie können die Eigenschaften der **Mediation Server PSTN-Gateway** Einstellungen in diesem Dialogfeld bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="c61c5-105">You edit the properties of the **Mediation Server PSTN gateway** settings in this dialog.</span></span> <span data-ttu-id="c61c5-106">Definieren Sie die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="c61c5-106">You define the following settings:</span></span>
  
- <span data-ttu-id="c61c5-107">Wählen Sie die **verbundener Vermittlungsserver aktiviert** , wenn Sie den Vermittlungsserver mit diesem Front-End-Server oder Front-End-Pools zu verbinden möchten.</span><span class="sxs-lookup"><span data-stu-id="c61c5-107">Select the **Collocated Mediation Server enabled** if you want to collocate the Mediation Server with this Front End Server or Front End pools.</span></span>
    
- <span data-ttu-id="c61c5-108">**Überwachungsports**: Definieren Sie die Ports, die der Vermittlungsserver überwacht wird.</span><span class="sxs-lookup"><span data-stu-id="c61c5-108">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="c61c5-109">Sie können einen Port für **TLS** oder Transport Layer Security oder **TCP**, definieren oder transport Control-Protokoll.</span><span class="sxs-lookup"><span data-stu-id="c61c5-109">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="c61c5-110">Für den Porteintrag für TCP verfügbar sein soll müssen Sie das Kontrollkästchen für **Aktivieren TCP-Port**auswählen.</span><span class="sxs-lookup"><span data-stu-id="c61c5-110">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="c61c5-111">Finden Sie in der Dokumentation und Konfiguration Einstellungen für Ihre Gateway public switched Telephone Network, (PSTN) zu ermitteln, wenn Sie bei aktivierter definieren müssen Port TLS, TCP oder beide Werte.</span><span class="sxs-lookup"><span data-stu-id="c61c5-111">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="c61c5-112">TLS ist eine sicherere Protokoll, Verwendung von Zertifikaten zur Verschlüsselung des Datenverkehrs zwischen dem Vermittlungsserver und PSTN-Gateway.</span><span class="sxs-lookup"><span data-stu-id="c61c5-112">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="c61c5-113">Nicht alle PSTN-Gateways unterstützt TLS.</span><span class="sxs-lookup"><span data-stu-id="c61c5-113">Not all PSTN gateways support TLS.</span></span> 
  
- <span data-ttu-id="c61c5-114">Auflistung des momentan zugeordneten und vorhandenen **Trunks** (Session Initiation Protocol-Trunk (SIP)), **Gateways** (PSTN-Gateway oder IP-PBX) und **Standorts** (für Trunk und Gateway konfigurierter Standort).</span><span class="sxs-lookup"><span data-stu-id="c61c5-114">A listing of currently associated and existing **Trunk** (that is, Session Initiation Protocol (SIP) Trunks), **Gateway** (PSTN gateway or IP-PBX) and **Site** (configured site for the trunk and gateway).</span></span>
    
- <span data-ttu-id="c61c5-p105">Wählen Sie einen Trunk, ein Gateway und einen Standort aus, und klicken Sie auf **Als Standardeinstellung festlegen**, um die Auswahl als Standardeinstellung für diesen Vermittlungsdienst festzulegen. Um die Auswahl als Standardeinstellung aufzuheben, wählen Sie die aktuelle Standardeinstellung aus und klicken Sie auf **Festlegung als Standardeinstellung aufheben**. Wählen Sie anschließend eine neue Standardeinstellung aus und klicken Sie auf **Als Standardeinstellung festlegen**.</span><span class="sxs-lookup"><span data-stu-id="c61c5-p105">You select a Trunk, Gateway and Site and click **Make Default** to set the selection as the default for this Mediation service. You select the current default and click **Unmake Default** to remove the selection as the current default. You then select a new default and click **Make Default**.</span></span>
    
 <span data-ttu-id="c61c5-118">**OK**: Mit dieser Option werden die Änderungen am Dialogfeld akzeptiert und übernommen.</span><span class="sxs-lookup"><span data-stu-id="c61c5-118">**OK** Accepts and commits changes to the dialog.</span></span>
  
 <span data-ttu-id="c61c5-119">**Abbrechen**: Mit dieser Option werden die Änderungen verworfen und das Dialogfeld wird geschlossen.</span><span class="sxs-lookup"><span data-stu-id="c61c5-119">**Cancel** Discards changes and closes the dialog.</span></span>
  
 <span data-ttu-id="c61c5-120">**Hilfe**: Mit dieser Option zeigen Sie diese Hilfeseite an.</span><span class="sxs-lookup"><span data-stu-id="c61c5-120">**Help** Displays this help screen.</span></span>
  

