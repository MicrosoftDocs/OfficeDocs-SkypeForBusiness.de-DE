---
title: Einstellungen für den Vermittlungsdienst für Lync Server 2010 – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 230e0a08-9e16-4bbd-b550-1f04bad8ddbc
description: 'Sie bearbeiten die Eigenschaften des Vermittlungsdiensts, indem Sie die folgenden Eigenschaften definieren:'
ms.openlocfilehash: 51fbd889d7e9d673fb75b1062a70ae55a9f8585c
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215106"
---
# <a name="mediation-service-settings-expander-for-lync-server-2010"></a><span data-ttu-id="e4aaa-103">Einstellungen für den Vermittlungsdienst für Lync Server 2010 – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="e4aaa-103">Mediation Service Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="e4aaa-104">Sie bearbeiten die Eigenschaften des Vermittlungsdiensts, indem Sie die folgenden Eigenschaften definieren:</span><span class="sxs-lookup"><span data-stu-id="e4aaa-104">You edit the properties of the Mediation service by defining the following properties:</span></span>
  
- <span data-ttu-id="e4aaa-p101">**Überwachungsports**: Definieren Sie den **TLS**-Port, der vom Vermittlungsdienst überwacht wird. Standardmäßig lautet der Portwert "TCP 5067" mit Transport Layer Security (TLS).</span><span class="sxs-lookup"><span data-stu-id="e4aaa-p101">**Listening ports**: Define the **TLS** port that the Mediation service will listen on. By default, the port value is TCP 5067 over transport layer security (TLS)</span></span>
    
    <span data-ttu-id="e4aaa-p102">Optional können Sie einen **TCP**-Portwert definieren. Standardmäßig lautet der Wert "TCP 5068".</span><span class="sxs-lookup"><span data-stu-id="e4aaa-p102">Optionally, you define a **TCP** port value. By default, the value is TCP 5068.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e4aaa-p103">Sie aktivieren die Einstellung für den TCP-Portwert, indem Sie **TCP-Port aktivieren** auswählen. Die Porteinstellungen, die für die Kommunikation mit dem Vermittlungsdienst erforderlich sind, finden Sie in der Dokumentation zum PSTN-Gateway (Public Switched Telephone Network) oder IP-PBX (Internet Protocol Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="e4aaa-p103">The TCP port value setting is enabled by selecting **Enable TCP port**. You should refer to the documentation for your Public Switched Telephone Network (PSTN) Gateway or Internet Protocol Private Branch Exchange (IP-PBX) for the requirements for the port settings required to communicate with the Mediation service.</span></span> 
  
- <span data-ttu-id="e4aaa-111">Verwenden Sie die Option **TCP-Port aktivieren**, um den Portwert für die TCP-Kommunikation über das PSTN-Gateway oder IP-PBX zu definieren.</span><span class="sxs-lookup"><span data-stu-id="e4aaa-111">You **Enable TCP port** to define the port value for TCP communications from your PSTN gateway or IP-PBX.</span></span>
    
- <span data-ttu-id="e4aaa-112">Auflistung des momentan zugeordneten und vorhandenen **Trunks** (Session Initiation Protocol-Trunks (SIP)), **Gateways** (PSTN-Gateway oder IP-PBX) und **Standorts** (für Trunk und Gateway konfigurierter Standort).</span><span class="sxs-lookup"><span data-stu-id="e4aaa-112">A listing of currently associated and existing **Trunk** (that is, Session Initiation Protocol (SIP) Trunks), **Gateway** (PSTN gateway or IP-PBX) and **Site** (configured site for the trunk and gateway).</span></span>
    
- <span data-ttu-id="e4aaa-p104">Wählen Sie einen Trunk, ein Gateway und einen Standort aus, und klicken Sie auf **Als Standardeinstellung festlegen**, um die Auswahl als Standardeinstellung für diesen Vermittlungsdienst festzulegen. Um die Auswahl als Standardeinstellung aufzuheben, wählen Sie die aktuelle Standardeinstellung aus und klicken auf **Festlegung als Standardeinstellung aufheben**. Wählen Sie anschließend eine neue Standardeinstellung aus, und klicken Sie auf **Als Standardeinstellung festlegen**.</span><span class="sxs-lookup"><span data-stu-id="e4aaa-p104">You select a Trunk, Gateway and Site and click **Make Default** to set the selection as the default for this Mediation service. You select the current default and click **Unmake Default** to remove the selection as the current default. You then select a new default and click **Make Default**.</span></span>
    
  <span data-ttu-id="e4aaa-116">**OK**: Mit dieser Option werden die Änderungen am Dialogfeld akzeptiert und übernommen.</span><span class="sxs-lookup"><span data-stu-id="e4aaa-116">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="e4aaa-117">**Abbrechen**: Mit dieser Option werden die Änderungen verworfen, und das Dialogfeld wird geschlossen.</span><span class="sxs-lookup"><span data-stu-id="e4aaa-117">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="e4aaa-118">**Hilfe**: Mit dieser Option zeigen Sie diese Hilfeseite an.</span><span class="sxs-lookup"><span data-stu-id="e4aaa-118">**Help** Displays this help screen.</span></span>
  

