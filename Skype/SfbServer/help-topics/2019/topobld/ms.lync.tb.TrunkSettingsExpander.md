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
localization_priority: Normal
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
ROBOTS: NOINDEX, NOFOLLOW
description: 'Führen Sie zum Bearbeiten oder Ändern der Einstellungen für einen SIP-Trunk die folgenden Aufgaben aus:'
ms.openlocfilehash: 43cce7d0e61cf2e2c4f5fa6e4bcb845fd63fbc03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807535"
---
# <a name="trunk-settings-expander"></a>Trunkeinstellungen – Erweiterung

Führen Sie zum Bearbeiten oder Ändern der Einstellungen für einen SIP-Trunk die folgenden Aufgaben aus:

 **Trunkname** ist eine erforderliche Angabe, mit der der SIP-Trunk in der Bereitstellung eindeutig identifiziert wird.

 **Zugeordnetes PSTN-Gateway**: Wählen Sie ein vorhandenes PSTN-Gateway aus, das in der Bereitstellung definiert wurde.

 **Überwachungsport für IP/PSTN-Gateway**: Gibt an, über welchen TCP/IP-Port das Gateway das System auf Anforderungen überwacht. Der erforderliche Wert kann abhängig vom Gatewayhersteller variieren, der Standardwert lautet jedoch Port 5067.

 **SIP-Transportprotokoll**: Als Protokoll wird entweder TCP oder TLS verwendet. Als Standardeinstellung ist TLS festgelegt. In der Dokumentation des Gatewayherstellers finden Sie die von Ihrem Gateway unterstützten Protokolle. Wenn das Gateway TLS unterstützt, ist die Standardeinstellung "TLS" die Option mit höherer Sicherheit.

 **Zugeordneter Vermittlungsserver:** Wählen Sie einen vorhandenen Vermittlungsserver aus der Bereitstellung aus, der dem SIP-Trunk zugeordnet werden soll.

> [!NOTE]
> Nur der Stamm trunk kann einem Vermittlungsserver zugeordnet werden.

 **Zugeordneter Vermittlungsserverport:** Ein erforderlicher Wert, der auf den Wert festgelegt ist, für den der Vermittlungsserver für die Abhörung konfiguriert ist.

![Trunkeinstellungen – Erweiterung](../../../media/Trunk_Settings_Expander.jpg)

## <a name="see-also"></a>Weitere Informationen

[Prüfliste für die Bereitstellung von SIP-Trunking](https://technet.microsoft.com/library/94f4f03e-19d5-4198-92be-e4076dbb959a.aspx)

[Komponenten und Topologien für das SIP-Trunking](https://technet.microsoft.com/library/8ed9a9d0-517e-4f36-a131-22cdafa257fa.aspx)
