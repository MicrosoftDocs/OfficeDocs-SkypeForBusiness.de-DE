---
title: Unterstützung mehrerer Trunks in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Skype for Business Server Funktionalität unterstützt mehrere Zuordnungen zwischen Gateways und Vermittlungsservern. Diese Zuordnungen werden durch Definieren eines Trunks vorgenommen, bei dem es sich um eine logische Zuordnung zwischen einem Vermittlungsserverpool und einem PSTN-Gateway, session Border Controller (SBC) oder einer IP-Nebenstellenanlage handelt. Verwenden Sie den Topologie-Generator, um Gateways Vermittlungsservern (d. a. Trunks) zuzuordnen.
ms.openlocfilehash: 0e4bc7d0248fa9116651a1384a17a7a8347b2d8f
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58729044"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a>Unterstützung mehrerer Trunks in Skype for Business Server

Skype for Business Server Funktionalität unterstützt mehrere Zuordnungen zwischen Gateways und Vermittlungsservern. Diese Zuordnungen werden durch Definieren eines Trunks vorgenommen, bei dem es sich um eine logische Zuordnung zwischen einem Vermittlungsserverpool und einem PSTN-Gateway, session Border Controller (SBC) oder einer IP-Nebenstellenanlage handelt. Verwenden Sie den Topologie-Generator, um Gateways Vermittlungsservern (d. a. Trunks) zuzuordnen.

- Um einen Trunk in Skype for Business Server zuzuweisen oder zu entfernen, müssen Sie zuerst einen Trunk im Topologie-Generator definieren. Ein Trunk besteht aus der folgenden Zuordnung: Vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Vermittlungsservers, Gateway-FQDN und Gateway-Überwachungsport.
- Um mehrere Trunks zu konfigurieren, können Sie mehrere Zuordnungen zwischen demselben Gateway und dem Vermittlungsserver erstellen. Dies bietet zusätzliche Resilienz für die Enterprise-VoIP Infrastruktur, was besonders in interoperationalen Szenarien mit Nebenstellenanlagen (Private Branch Exchange, PBX) nützlich ist. 

Beim Definieren eines Trunks muss er einer Route zugeordnet werden. Um einen Trunk einer Route zuzuordnen, definieren Sie einen einfachen Namen für den Trunk im Topologie-Generator. Dieser einfache Name wird als Trunkname in der Skype for Business Server Systemsteuerung verwendet, wobei Trunks Routen zugeordnet werden können. Der einfache Trunkname wird als Gatewayname aus der Skype for Business Server Verwaltungsshell verwendet.

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

Der Administrator muss einen Standardtrunk auswählen, der einem Vermittlungsserver zugeordnet ist. Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den zugeordneten Vermittlungsserver, und klicken Sie dann auf **"Eigenschaften".** Geben Sie das Standardgateway für den Vermittlungsserver an. 

Das folgende Diagramm veranschaulicht die mehreren Trunks, die für jeden Vermittlungsserver und jedes Gateway definiert sind. 

![Mehrere Trunkzuweisungen.](../../media/multiple-trunk-assignments.jpg)
