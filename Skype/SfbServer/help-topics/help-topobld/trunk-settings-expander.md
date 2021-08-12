---
title: Trunkeinstellungen – Erweiterung
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
description: 'Führen Sie zum Bearbeiten oder Ändern der Einstellungen für einen SIP-Trunk die folgenden Aufgaben aus:'
ms.openlocfilehash: c29f7e62b047e06bfce20324a7edc8dc33d635ac416fb78ae31efaba63538141
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54290612"
---
# <a name="trunk-settings-expander"></a>Trunkeinstellungen – Erweiterung

Führen Sie zum Bearbeiten oder Ändern der Einstellungen für einen SIP-Trunk die folgenden Aufgaben aus:

 **Trunkname** ist eine erforderliche Angabe, mit der der SIP-Trunk in der Bereitstellung eindeutig identifiziert wird.

 **Zugeordnetes PSTN-Gateway**: Wählen Sie ein vorhandenes PSTN-Gateway aus, das in der Bereitstellung definiert wurde.

 **Überwachungsport für IP/PSTN-Gateway**: Gibt an, über welchen TCP/IP-Port das Gateway das System auf Anforderungen überwacht. Der erforderliche Wert kann abhängig vom Gatewayhersteller variieren, der Standardwert lautet jedoch Port 5067.

 **SIP-Transportprotokoll**: Als Protokoll wird entweder TCP oder TLS verwendet. Als Standardeinstellung ist TLS festgelegt. In der Dokumentation des Gatewayherstellers finden Sie die von Ihrem Gateway unterstützten Protokolle. Wenn das Gateway TLS unterstützt, ist die Standardeinstellung "TLS" die Option mit höherer Sicherheit.

 **Zugeordneter Vermittlungsserver:** Wählen Sie einen vorhandenen Vermittlungsserver aus der Bereitstellung aus, der dem SIP-Trunk zugeordnet werden soll.

> [!NOTE]
> Nur der Stammtrunk kann einem Lync Server 2010- oder Lync Server 2013-Vermittlungsserver zugeordnet werden.

 **Zugeordneter Vermittlungsserverport:** Ein erforderlicher Wert, der auf den Wert festgelegt ist, den der Vermittlungsserver für das Überwachen konfiguriert hat.

![Trunkeinstellungen – Erweiterung](../../media/Trunk_Settings_Expander.jpg)

## <a name="see-also"></a>Siehe auch

[Prüfliste für die Bereitstellung von SIP-Trunking](/previous-versions/office/lync-server-2013/lync-server-2013-sip-trunk-deployment-checklist)

[Komponenten und Topologien für das SIP-Trunking](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-sip-trunking)