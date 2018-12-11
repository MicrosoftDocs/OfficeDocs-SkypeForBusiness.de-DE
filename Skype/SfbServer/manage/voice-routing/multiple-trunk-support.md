---
title: Unterstützung mehrerer Trunks in Skype für Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype-Funktionen, Business Server unterstützt mehrere Zuordnungen zwischen Gateways und Vermittlungsservern. Diese Zuordnungen werden geändert, indem ein Trunk eine logische Zuordnung zwischen einem vermittlungsserverpool und einem Gateway public switched Telephone Network (Telefonfestnetz PSTN), Session Border Controller (SBC) oder IP-PBX ist zu definieren. Verwenden Sie den Topologie-Generator Vermittlungsserver (d. h., Trunks) Gateways zugeordnet.
ms.openlocfilehash: 086d345eb7492423526466cc77a2ce0d0d9a998e
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222786"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a>Unterstützung mehrerer Trunks in Skype für Business Server

Skype-Funktionen, Business Server unterstützt mehrere Zuordnungen zwischen Gateways und Vermittlungsservern. Diese Zuordnungen werden geändert, indem ein Trunk eine logische Zuordnung zwischen einem vermittlungsserverpool und einem Gateway public switched Telephone Network (Telefonfestnetz PSTN), Session Border Controller (SBC) oder IP-PBX ist zu definieren. Verwenden Sie den Topologie-Generator Vermittlungsserver (d. h., Trunks) Gateways zugeordnet.

- Zum Zuweisen oder Entfernen eines Trunks in Skype für Business Server, müssen Sie zuerst einen Trunk im Topologie-Generator definieren. Ein Trunk umfasst die folgenden Zuordnung: Vermittlungsserver vollqualifizierter Domänenname (FQDN), den Vermittlungsserver Überwachungsport, FQDN des Gateways und den Überwachungsport des Gateways.
- Um mehrere Trunks zu konfigurieren, können Sie mehrere Zuordnungen zwischen dem gleichen Gateway und dem Vermittlungsserver erstellen. Dadurch wird die zusätzliche Flexibilität mit der Enterprise-VoIP-Infrastruktur in private Branch Exchange, (Nebenstellenanlage PBX) interoperational Szenarien besonders nützlich ist. 

Beim Definieren eines Trunks muss er einer Route zugeordnet werden. Um einen Trunk einer Route zuzuordnen, definieren Sie einen einfachen Namen für die Trunks im Topologie-Generator. Diese einfache Name wird als den trunknamen in der Skype Business Server-Systemsteuerung verwendet, in dem Trunks Routen zugeordnet werden kann. Der einfachen trunknamen dient als Gateway-Namen aus der Skype für Business Server-Verwaltungsshell.

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

Der Administrator muss einen Standard-Trunk zugeordnet eines Vermittlungsservers auswählen. Topologie-Generator mit der rechten Maustaste zugeordneter Vermittlungsserver, und klicken Sie dann auf **Eigenschaften**. Geben Sie den Standard-Gateway für den Vermittlungsserver. 

Das folgende Diagramm veranschaulicht die mehrere Trunks, die für jeden Vermittlungsserver und dem Gateway definiert sind. 

![Mehrere Trunk-Zuordnungen](../../media/multiple-trunk-assignments.jpg)