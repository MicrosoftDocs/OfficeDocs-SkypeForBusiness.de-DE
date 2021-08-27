---
title: Trunkeinstellungen – Erweiterung
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
ROBOTS: NOINDEX, NOFOLLOW
description: 'Führen Sie zum Bearbeiten oder Ändern der Einstellungen für einen SIP-Trunk die folgenden Aufgaben aus:'
ms.openlocfilehash: 32b25ceae180fd252a0b7cba64124c45d2e330a0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58579159"
---
# <a name="trunk-settings-expander"></a>Trunkeinstellungen – Erweiterung

Führen Sie zum Bearbeiten oder Ändern der Einstellungen für einen SIP-Trunk die folgenden Aufgaben aus:

 **Trunkname** ist eine erforderliche Angabe, mit der der SIP-Trunk in der Bereitstellung eindeutig identifiziert wird.

 **Zugeordnetes PSTN-Gateway**: Wählen Sie ein vorhandenes PSTN-Gateway aus, das in der Bereitstellung definiert wurde.

 **Überwachungsport für IP/PSTN-Gateway**: Gibt an, über welchen TCP/IP-Port das Gateway das System auf Anforderungen überwacht. Der erforderliche Wert kann abhängig vom Gatewayhersteller variieren, der Standardwert lautet jedoch Port 5067.

 **SIP-Transportprotokoll**: Als Protokoll wird entweder TCP oder TLS verwendet. Als Standardeinstellung ist TLS festgelegt. In der Dokumentation des Gatewayherstellers finden Sie die von Ihrem Gateway unterstützten Protokolle. Wenn das Gateway TLS unterstützt, ist die Standardeinstellung "TLS" die Option mit höherer Sicherheit.

 **Zugeordneter Vermittlungsserver:** Wählen Sie einen vorhandenen Vermittlungsserver aus der Bereitstellung aus, der dem SIP-Trunk zugeordnet werden soll.

> [!NOTE]
> Einem Vermittlungsserver kann nur der Stammtrunk zugeordnet werden.

 **Zugeordneter Vermittlungsserverport:** Ein erforderlicher Wert, der auf den Wert festgelegt ist, den der Vermittlungsserver für das Überwachen konfiguriert hat.

![Trunkeinstellungen – Erweiterung](../../../media/Trunk_Settings_Expander.jpg)

## <a name="see-also"></a>Siehe auch

[Prüfliste für die Bereitstellung von SIP-Trunking](/previous-versions/office/lync-server-2013/lync-server-2013-sip-trunk-deployment-checklist)

[Komponenten und Topologien für das SIP-Trunking](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-sip-trunking)