---
title: Servereinstellungen für Lync Server 2010 – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: 'Gehen Sie wie folgt vor, um die Eigenschaften für diesen Computer zu bearbeiten:'
ms.openlocfilehash: 28261b3637040acda70218f23101b4337b1f90c3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297610"
---
# <a name="server-settings-expander-for-lync-server-2010"></a>Servereinstellungen für Lync Server 2010 – Erweiterung
 
Gehen Sie wie folgt vor, um die Eigenschaften für diesen Computer zu bearbeiten:
  
- Bearbeiten Sie den **vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN)** für diesen Computer. Dieser Eintrag muss mit dem Computernamen übereinstimmen, wie er im DNS (Domain Name System) definiert ist, sowie in "Subject Alternative Names (San)" oder "Subject Name (SN)" des Zertifikats, das diesem Computer zugeordnet ist.
    
- Wählen Sie eine der folgenden Optionen aus:
    
    **Alle konfigurierten IP-Adressen verwenden**: Wählen Sie diese Option aus, um alle konfigurierten IP-Adressen auf dem Computer zu verwenden.
    
    > [!IMPORTANT]
    > Wenn der Computer über mehrere IP-Adressen verfügt, müssen Sie beachten, dass die diesem Computer zugeordneten Dienste alle IP-Adressen für alle Dienste verwenden werden. Wenn ein Überwachungsserver oder-Dienst die Kommunikation mit einer bestimmten IP-Adresse und einem Port erwartet, kann der Dienst möglicherweise nicht die beste Auswahl für die IP-Adresse treffen, die Sie abhören möchten. 
  
    **Einschränken der Dienstnutzung auf ausgewählte IP-Adressen**: Wählen Sie diese Option aus, wenn Sie bestimmte IP-Adressen für die **primäre IP-Adresse** definieren möchten, die dieser Computer für die Kommunikation von anderen Computern und Pools in der Bereitstellung überwacht. Definieren Sie die **PSTN-IP-Adresse** für die spezifische IP-Adresse, die der Computer und Dienst für die Kommunikation überwacht, und senden Sie die Kommunikation an das definierte PSTN-Gateway oder die IP-Telefonanlage.
    

