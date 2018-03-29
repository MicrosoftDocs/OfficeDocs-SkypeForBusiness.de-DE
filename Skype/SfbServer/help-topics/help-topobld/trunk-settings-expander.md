---
title: Trunkeinstellungen – Erweiterung
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
description: 'Führen Sie zum Bearbeiten oder Ändern der Einstellungen für einen SIP-Trunk die folgenden Aufgaben aus:'
ms.openlocfilehash: 13ea9abfb6d53b57333c2c96b8a2f8adde963ebf
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="trunk-settings-expander"></a>Trunkeinstellungen – Erweiterung
 
Führen Sie zum Bearbeiten oder Ändern der Einstellungen für einen SIP-Trunk die folgenden Aufgaben aus:
  
 **Trunkname** ist eine erforderliche Angabe, mit der der SIP-Trunk in der Bereitstellung eindeutig identifiziert wird.
  
 **Zugeordnetes PSTN-Gateway**: Wählen Sie ein vorhandenes PSTN-Gateway aus, das in der Bereitstellung definiert wurde.
  
 **Überwachungsport für IP/PSTN-Gateway**: Gibt an, über welchen TCP/IP-Port das Gateway das System auf Anforderungen überwacht. Der erforderliche Wert kann abhängig vom Gatewayhersteller variieren, der Standardwert lautet jedoch Port 5067.
  
 **SIP-Transportprotokoll**: Als Protokoll wird entweder TCP oder TLS verwendet. Als Standardeinstellung ist TLS festgelegt. In der Dokumentation des Gatewayherstellers finden Sie die von Ihrem Gateway unterstützten Protokolle. Wenn das Gateway TLS unterstützt, ist die Standardeinstellung „TLS“ die Option mit höherer Sicherheit.
  
 **Zugeordneter Vermittlungsserver**: Wählen Sie eine vorhandene Vermittlungsserver aus der Bereitstellung der SIP-Trunk zugeordnet.
  
> [!NOTE]
> Nur der stammtrunk kann mit einem Lync Server 2010 oder Lync Server 2013-Vermittlungsservers zugeordnet werden. 
  
 **Zugeordneter Vermittlungsserver Port**: ein erforderlicher Wert, dies ist festgelegt auf den Wert, der den Vermittlungsserver konfiguriert ist lauschen.
  
![Trunkeinstellungen – Erweiterung](../../media/Trunk_Settings_Expander.jpg)
  
## <a name="see-also"></a>Siehe auch

#### 

[Prüfliste für die Bereitstellung von SIP-Trunking](http://technet.microsoft.com/library/94f4f03e-19d5-4198-92be-e4076dbb959a.aspx)
  
[Komponenten und Topologien für SIP-Trunking](http://technet.microsoft.com/library/8ed9a9d0-517e-4f36-a131-22cdafa257fa.aspx)

