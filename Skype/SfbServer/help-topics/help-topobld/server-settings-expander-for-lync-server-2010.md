---
title: Servereinstellungen für Lync Server 2010 – Erweiterung
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: 'Führen Sie die folgenden Schritte aus, um die Eigenschaften für diesen Computer zu bearbeiten:'
---

# <a name="server-settings-expander-for-lync-server-2010"></a>Servereinstellungen für Lync Server 2010 – Erweiterung
 
Führen Sie die folgenden Schritte aus, um die Eigenschaften für diesen Computer zu bearbeiten:
  
- Bearbeiten Sie unter **Vollqualifizierter Domänenname (FQDN)** den FQDN für diesen Computer. Dieser Eintrag muss mit dem Computernamen übereinstimmen, der im Domain Name System (DNS) und in den alternativen Antragstellernamen (SAN) bzw. Antragstellernamen (SN) des Zertifikats für diesen Computer angegeben ist.
    
- Wählen Sie eine der folgenden Optionen aus:
    
    **Alle konfigurierten IP-Adressen verwenden**: Wählen Sie diese Option aus, um alle auf dem Computer konfigurierten IP-Adressen zu verwenden.
    
    > [!IMPORTANT]
    > Beachten Sie bei mehreren auf dem Computer vorhandenen IP-Adressen, dass für die Dienste, die diesem Computer zugeordnet sind, alle IP-Adressen für alle Dienste verwendet werden. Wenn ein Überwachungsserver oder -dienst eine Kommunikation von einer bestimmten IP-Adresse und dem dazugehörigen Port erwartet, wird für den Dienst möglicherweise nicht die beste IP-Adresse für die Überwachung gewählt. 
  
    **Dienstnutzung auf die ausgewählten IP-Adressen beschränken**: Wählen Sie diese Option aus, wenn Sie bestimmte IP-Adressen als **Primäre IP-Adresse** definieren möchten, über die der Computer eine Kommunikation mit anderen Computern und Pools der Bereitstellung erwartet. Definieren Sie die **PSTN-IP-Adresse** für die jeweilige IP-Adresse, über die der Computer und der Dienst die Kommunikation erwartet und Kommunikationsdaten an das definierte PSTN-Gateway oder die Festnetztelefonanlage sendet.
    

