---
title: Servereinstellungen für Lync Server 2010 – Erweiterung
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: 'Um die Eigenschaften für diesen Computer zu bearbeiten, führen Sie die folgenden Aufgaben:'
ms.openlocfilehash: 4b05c52d92d3702c76afd6c7b682c1c9ffda7ab9
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219205"
---
# <a name="server-settings-expander-for-lync-server-2010"></a>Servereinstellungen für Lync Server 2010 – Erweiterung
 
Um die Eigenschaften für diesen Computer zu bearbeiten, führen Sie die folgenden Aufgaben:
  
- Bearbeiten Sie den **vollqualifizierten Domänennamen (FQDN)** für diesen Computer. Bei diesem Eintrag muss den Namen des Computers übereinstimmen, wie er im Domain Name System (DNS) und im alternativen Antragstellernamen (SAN) oder Antragstellername (SN) des Zertifikats, die diesem Computer zugeordnet definiert wird.
    
- Wählen Sie eine der folgenden:
    
    **Alle konfigurierte IP-Adressen verwenden**: Wählen Sie diese Option, um alle konfigurierten IP-Adressen auf dem Computer verwenden.
    
    > [!IMPORTANT]
    > Wenn der Computer über mehrere IP-Adressen verfügt, müssen Sie beachten Sie, dass die Dienste, die diesem Computer zugeordnet alle IP-Adressen für alle Dienste verwendet werden. Wenn ein überwachenden Server oder Dienst Kommunikation einer bestimmten IP-Adresse und Port erwartet, kann der Dienst nicht die beste Auswahl an welche IP-Adresse abhören stellen. 
  
    **Verwendung von Grenzwert ausgewählten IP-Adressen**: Wählen Sie diese Option aus, wenn Sie bestimmte IP-Adressen für die **primäre IP-Adresse** , die diesem Computer für die Kommunikation von anderen Computer und Pools in der Bereitstellung überwacht wird, definieren möchten. Definieren von **PSTN-IP-Adresse** für die spezifischen IP-Adresse, dass der Computer und -Dienst für die Kommunikation abhören und Communications an die definierte PSTN-Gateway oder IP-PBX senden werden.
    

