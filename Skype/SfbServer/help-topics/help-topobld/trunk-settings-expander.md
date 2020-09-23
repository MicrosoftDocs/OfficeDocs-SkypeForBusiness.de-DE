---
title: Trunkeinstellungen – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 6393ef52859f32ad93d363faf36af3bd34530a9b
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215936"
---
# <a name="trunk-settings-expander"></a>Trunkeinstellungen – Erweiterung

Führen Sie zum Bearbeiten oder Ändern der Einstellungen für einen SIP-Trunk die folgenden Aufgaben aus:

 **Trunkname** ist eine erforderliche Angabe, mit der der SIP-Trunk in der Bereitstellung eindeutig identifiziert wird.

 **Zugeordnetes PSTN-Gateway**: Wählen Sie ein vorhandenes PSTN-Gateway aus, das in der Bereitstellung definiert wurde.

 **Überwachungsport für IP/PSTN-Gateway**: Gibt an, über welchen TCP/IP-Port das Gateway das System auf Anforderungen überwacht. Der erforderliche Wert kann abhängig vom Gatewayhersteller variieren, der Standardwert lautet jedoch Port 5067.

 **SIP-Transportprotokoll**: Als Protokoll wird entweder TCP oder TLS verwendet. Als Standardeinstellung ist TLS festgelegt. In der Dokumentation des Gatewayherstellers finden Sie die von Ihrem Gateway unterstützten Protokolle. Wenn das Gateway TLS unterstützt, ist die Standardeinstellung "TLS" die Option mit höherer Sicherheit.

 **Zugeordnete Vermittlungsserver**: Wählen Sie einen vorhandenen Vermittlungsserver aus der Bereitstellung aus, der dem SIP-Trunk zugeordnet werden soll.

> [!NOTE]
> Nur der Stamm trunk kann einem lync Server 2010 oder lync Server 2013 Vermittlungsserver zugeordnet werden.

 **Zugeordneter Vermittlungsserver Port**: ein erforderlicher Wert, der auf den Wert festgelegt ist, den der Vermittlungsserver für die Überwachung konfiguriert hat.

![Trunkeinstellungen – Erweiterung](../../media/Trunk_Settings_Expander.jpg)

## <a name="see-also"></a>Siehe auch

[Prüfliste zur SIP-Trunking-Bereitstellung](https://technet.microsoft.com/library/94f4f03e-19d5-4198-92be-e4076dbb959a.aspx)

[Komponenten und Topologien für das SIP-Trunking](https://technet.microsoft.com/library/8ed9a9d0-517e-4f36-a131-22cdafa257fa.aspx)
