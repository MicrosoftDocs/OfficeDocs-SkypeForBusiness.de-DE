---
title: PowerShell-Skript zum Testen der Verbindungen des direkten Routing Sitzung-Grenz Controllers
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: Verwenden Sie dieses PowerShell-Skriptbeispiel, um direkte Routing Sitzung-Grenz Controller Verbindungen in Microsoft Teams zu testen.
localization_priority: Normal
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: c6df8ee654696ceef89c36a354d943c97139bf8b
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37568677"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a><span data-ttu-id="6aa59-103">PowerShell-Skript zum Testen der Verbindungen des direkten Routing Sitzung-Grenz Controllers</span><span class="sxs-lookup"><span data-stu-id="6aa59-103">PowerShell script to test Direct Routing Session Border Controller connections</span></span>

<span data-ttu-id="6aa59-104">Der SIP-Tester-Client ist ein Beispiel für ein PowerShell-Skript, das Sie zum Testen von SBC-Verbindungen (Direct Routing Session Border Controller) in Microsoft Teams verwenden können.</span><span class="sxs-lookup"><span data-stu-id="6aa59-104">SIP Tester client is a sample PowerShell script that you can use to test Direct Routing Session Border Controller (SBC) connections in Microsoft Teams.</span></span> <span data-ttu-id="6aa59-105">Dieses Skript testet die grundlegenden Funktionen eines Kunden gekoppelten SIP-Trunks (Session Initiation Protocol) mit direktem Routing.</span><span class="sxs-lookup"><span data-stu-id="6aa59-105">This script tests basic functionality of a customer-paired Session Initiation Protocol (SIP) trunk with Direct Routing.</span></span>

<span data-ttu-id="6aa59-106">Das Skript übermittelt einen SIP-Test an den Test Runner, wartet auf das Ergebnis und zeigt es dann in einem menschlich lesbaren Format an.</span><span class="sxs-lookup"><span data-stu-id="6aa59-106">The script submits an SIP test to the test runner, waits for the result, and then presents it in a human-readable format.</span></span> <span data-ttu-id="6aa59-107">Sie können dieses Skript verwenden, um die folgenden Szenarien zu testen:</span><span class="sxs-lookup"><span data-stu-id="6aa59-107">You can use this script to test the following scenarios:</span></span>

- <span data-ttu-id="6aa59-108">Ausgehende und eingehende Anrufe</span><span class="sxs-lookup"><span data-stu-id="6aa59-108">Outbound and inbound calls</span></span>
- <span data-ttu-id="6aa59-109">Simultaner Ring</span><span class="sxs-lookup"><span data-stu-id="6aa59-109">Simultaneous ring</span></span>
- <span data-ttu-id="6aa59-110">Medien Eskalation</span><span class="sxs-lookup"><span data-stu-id="6aa59-110">Media escalation</span></span>
- <span data-ttu-id="6aa59-111">Beratende Übertragung</span><span class="sxs-lookup"><span data-stu-id="6aa59-111">Consultative transfer</span></span>

## <a name="download-the-script-and-documentation"></a><span data-ttu-id="6aa59-112">Herunterladen des Skripts und der Dokumentation</span><span class="sxs-lookup"><span data-stu-id="6aa59-112">Download the script and documentation</span></span>

<span data-ttu-id="6aa59-113">Laden Sie das [SIP Tester-Clientskript und die Dokumentation](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true)herunter.</span><span class="sxs-lookup"><span data-stu-id="6aa59-113">Download the [SIP Tester client script and documentation](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).</span></span>