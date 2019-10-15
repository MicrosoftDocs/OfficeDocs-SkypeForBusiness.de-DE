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
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e5aeeea173a12e012a959b5fd37d802c6ea48c79
ms.sourcegitcommit: 0d7f3c7a84584ec25a23190187215109c8756189
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "37510756"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a>PowerShell-Skript zum Testen der Verbindungen des direkten Routing Sitzung-Grenz Controllers

Der SIP-Tester-Client ist ein Beispiel für ein PowerShell-Skript, das Sie zum Testen von SBC-Verbindungen (Direct Routing Session Border Controller) in Microsoft Teams verwenden können. Dieses Skript testet die grundlegenden Funktionen eines Kunden gekoppelten SIP-Trunks (Session Initiation Protocol) mit direktem Routing.

Das Skript übermittelt einen SIP-Test an den Test Runner, wartet auf das Ergebnis und zeigt es dann in einem menschlich lesbaren Format an. Sie können dieses Skript verwenden, um die folgenden Szenarien zu testen:

- Ausgehende und eingehende Anrufe
- Simultaner Ring
- Medien Eskalation
- Beratende Übertragung

## <a name="download-the-script-and-documentation"></a>Herunterladen des Skripts und der Dokumentation

Laden Sie das [SIP Tester-Clientskript und die Dokumentation](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/scripts/sip-tester-client/siptesterclient.zip?raw=true)herunter.