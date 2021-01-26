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
localization_priority: Normal
description: Die Skype for Business Server-Funktion unterstützt mehrere Zuordnungen zwischen Gateways und Vermittlungsservern. Diese Zuordnungen werden durch Definieren eines Trunks vorgenommen, bei dem es sich um eine logische Zuordnung zwischen einem Vermittlungsserverpool und einem PSTN-Gateway, einem SBC (Session Border Controller) oder einer IP-PBX-Anlage handelt. Verwenden Sie den Topologie-Generator, um Gateways Vermittlungsservern (d. h. Trunks) zuzuordnen.
ms.openlocfilehash: 0f4c8d2ee16c900ef666c12230964a9abb8f5a48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826225"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a>Unterstützung mehrerer Trunks in Skype for Business Server

Die Skype for Business Server-Funktionalität unterstützt mehrere Zuordnungen zwischen Gateways und Vermittlungsservern. Diese Zuordnungen werden durch Definieren eines Trunks vorgenommen, bei dem es sich um eine logische Zuordnung zwischen einem Vermittlungsserverpool und einem PSTN-Gateway, einem SBC (Session Border Controller) oder einer IP-PBX-Anlage handelt. Verwenden Sie den Topologie-Generator, um Gateways Vermittlungsservern (d. h. Trunks) zuzuordnen.

- Zum Zuweisen oder Entfernen eines Trunks in Skype for Business Server müssen Sie zunächst einen Trunk im Topologie-Generator definieren. Ein Trunk besteht aus der folgenden Zuordnung: Vollqualifizierter Domänenname (FQDN) des Vermittlungsservers, Abhörport des Vermittlungsservers, Gateway-FQDN und Gateway-Listening-Port.
- Zum Konfigurieren mehrerer Trunks können Sie mehrere Zuordnungen zwischen demselben Gateway und dem Vermittlungsserver erstellen. Dies bietet zusätzliche Resilienz für die Enterprise-VoIP, was besonders in Interoperationsszenarien mit Nebenstellenanlagen (Private Branch Exchange, PBX) hilfreich ist. 

Beim Definieren eines Trunks muss er einer Route zugeordnet werden. Zum Zuordnen eines Trunks zu einer Route definieren Sie einen einfachen Namen für den Trunk im Topologie-Generator. Dieser einfache Name wird als Trunkname in der Skype for Business Server-Systemsteuerung verwendet, wo Trunks Routen zugeordnet werden können. Der einfache Trunkname wird als Gatewayname aus der Skype for Business Server-Verwaltungsshell verwendet.

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

Der Administrator muss einen Standard trunk auswählen, der einem Vermittlungsserver zugeordnet ist. Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den zugeordneten Vermittlungsserver, und klicken Sie dann auf **Eigenschaften**. Geben Sie das Standardgateway für den Vermittlungsserver an. 

Das folgende Diagramm zeigt die mehreren Trunks, die für jeden Vermittlungsserver und jedes Gateway definiert sind. 

![Mehrere Trunkzuweisungen](../../media/multiple-trunk-assignments.jpg)
