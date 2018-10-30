---
title: 'Lync Server 2013: Unterstützung für mehrere Trunks'
TOCTitle: Unterstützung für mehrere Trunks
ms:assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205127(v=OCS.15)
ms:contentKeyID: 49294939
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Unterstützung für mehrere Trunks in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Die Lync Server 2013-Funktionalität unterstützt mehrere Zuordnungen zwischen Gateways und Vermittlungsservern. Die Zuordnungen werden durch die Definition eines Trunk vorgenommen. Dabei handelt es sich um eine logische Zuordnung zwischen einem Vermittlungsserverpool und einem PSTN-Gateway (Telefonfestnetz), SBC (Session Border Controller) oder einer IP-Festnetztelefonanlage. Verwenden Sie den Topologie-Generator zum Zuordnen von Gateways zu Vermittlungsservern (Trunks).

  - Wenn Sie einen Trunk in Lync Server 2013 zuordnen oder entfernen möchten, müssen Sie zunächst im Topologie-Generator einen Trunk definieren. Ein Trunk umfasst die folgende Zuordnung: vollqualifizierter Domänenname (Fully Qualified Domain Name, FQDN) des Vermittlungsservers, Überwachungsport des Vermittlungsservers, Gateway-FQDN und Gateway-Überwachungsport.

  - Wenn Sie mehrere Trunks konfigurieren möchten, können Sie mehrere Zuordnungen zwischen demselben Gateway und dem Vermittlungsserver erstellen. Dies führt zu einer zusätzlichen Ausfallsicherheit für die Enterprise-VoIP-Infrastruktur, was speziell in Interoperationalitätsszenarien mit Nebenstellenanlagen (Private Branch Exchange, PBX) besonders hilfreich ist.

Beim Definieren eines Trunks muss er einer Route zugeordnet werden. Zum Zuordnen eines Trunks zu einer Route definieren Sie im Topologie-Generator einen einfachen Namen für den Trunk. Dieser einfache Name dient als Trunkname in der Lync Server-Systemsteuerung, wo Trunks Routen zugeordnet werden können. Der einfache Trunkname wird von der Lync Server-Verwaltungsshell als Gatewayname verwendet.

    New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}

Der Administrator muss einen Standardtrunk auswählen, der einem Vermittlungsserver zugeordnet ist. Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den zugeordneten Vermittlungsserver, und klicken Sie dann auf **Eigenschaften** . Geben Sie das Standardgateway für den Vermittlungsserver an.

In der folgenden Abbildung werden mehrere Trunks veranschaulicht, die für jeden Vermittlungsserver und jedes Gateway definiert werden.

**M-N Trunk-Routing**

![Mehrere Trunk-Zuweisungen](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "Mehrere Trunk-Zuweisungen")

