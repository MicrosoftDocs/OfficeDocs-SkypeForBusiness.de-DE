---
title: Komponenten und Topologien für die Anrufsteuerung in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
description: Planen der Anrufannahme Steuerung (CAC), wenn Sie über ein MPLS-Netzwerk, einen SIP-Stamm oder ein PSTN-Gateway oder eine Telefonanlage eines Drittanbieters verfügen. Gilt für Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: 326387b7b0794b3cbd027d539880f8c4b40f42d8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277013"
---
# <a name="components-and-topologies-for-call-admission-control-in-skype-for-business"></a>Komponenten und Topologien für die Anrufsteuerung in Skype for Business

Planen der Anrufannahme Steuerung (CAC), wenn Sie über ein MPLS-Netzwerk, einen SIP-Stamm oder ein PSTN-Gateway oder eine Telefonanlage eines Drittanbieters verfügen. Gilt für Skype for Business Server Enterprise-VoIP.

Die Themen in diesem Abschnitt liefern Informationen zu speziellen Faktoren, die bei der Bereitstellung der Anrufsteuerung mit verschiedenen Typen von Netzwerktopologien berücksichtigt werden sollten.

## <a name="call-admission-control-on-an-mpls-network"></a>Anrufsteuerung in einem MPLS-Netzwerk

In einem MPLS-Netzwerk (Multiprotocol Label Switching) sind alle Standorte vollständig miteinander vernetzt, d. h. alle Standorte sind direkt mit dem MPLS-Backbone des Internetdienstanbieters verbunden und jedem Standort wird Bandbreite für eine WAN-Verbindung mit der MPLS-Cloud zur Verfügung gestellt. Es ist kein Netzwerkhub oder zentraler Standort zur Steuerung des IP-Routings vorhanden. Die folgende Abbildung zeigt ein einfaches Beispiel für ein auf der MPLS-Technologie basierendes Netzwerk.

**Beispiel eines MPLS-Netzwerks**

![Anrufsteuerung mit MPLS](../../media/CAC_MPLS_1.jpg)

Zur Bereitstellung der Anrufsteuerung (Call Admission Control, CAC) in einem MPLS-Netzwerk erstellen Sie eine Netzwerkregion für die MPLS-Cloud und Netzwerkstandorte für jeden MPLS-Zweigstellenstandort. Die folgende Abbildung zeigt, wie Netzwerkregion und Netzwerkstandorte konfiguriert sein sollten, um das MPLS-Beispielnetzwerk aus der Abbildung oben darzustellen. Die Bandbreitenbeschränkungen insgesamt sowie die Bandbreitenbeschränkung pro Sitzung basieren auf der Kapazität der WAN-Verbindung zwischen jedem Netzwerkstandort und der Netzwerkregion, die die MPLS-Cloud darstellt.

**Netzwerkregion und Netzwerkstandorte für ein MPLS-Netzwerk**

![Anrufsteuerung mit MPLS (Diagramm)](../../media/CAC_MPLS_2.jpg)

## <a name="call-admission-control-on-a-sip-trunk"></a>Anrufsteuerung für einen SIP-Trunk

Zur Bereitstellung der Anrufsteuerung für einen SIP-Trunk erstellen Sie einen Netzwerkstandort, der den Anbieter von Internettelefoniediensten repräsentiert. Um Bandbreitenrichtlinienwerte auf den SIP-Trunk anzuwenden, erstellen Sie eine standortübergreifende Richtlinie zwischen dem Netzwerkstandort in Ihrem Unternehmen und dem Netzwerkstandort, der für den Anbieter von Internettelefoniediensten erstellt wird.

Die folgende Abbildung zeigt ein Beispiel für die Bereitstellung der Anrufsteuerung für einen SIP-Trunk.

**Konfiguration der Anrufsteuerung für einen SIP-Trunk**

![Anrufsteuerung – SIP-Trunking (Diagramm)](../../media/CAC_SIP_trunk_1.jpg)

Zur Konfiguration der Anrufsteuerung für einen SIP-Trunk müssen Sie während der Bereitstellung der Anrufsteuerung die folgenden Aufgaben ausführen:

1. Erstellen eines Netzwerkstandorts, der den Anbieter von Internettelefoniediensten repräsentiert. Zuordnen des Netzwerkstandorts zu einer geeigneten Netzwerkregion und Zuweisen eines Bandbreitenwerts von Null für Audio und Video an diesem Netzwerkstandort. Ausführliche Informationen finden Sie unter [Configure Network Sites for CAC](https://technet.microsoft.com/library/afcea38f-5789-45ec-97af-c6e38364950c.aspx) in der Bereitstellungsdokumentation.

    > [!NOTE]
    > Für den Anbieter von Internettelefoniediensten ist diese Netzwerkstandortkonfiguration nicht funktionsfähig. Die Bandbreitenrichtlinienwerte werden tatsächlich in Schritt 2 angewendet.

2. Erstellen Sie einen Inter-Site-Link für den SIP-Trunk unter Verwendung der relevanten Parameterwerte für die Website, die Sie in Schritt 1 erstellt haben. Verwenden Sie beispielsweise den Namen der Netzwerk Website in Ihrem Unternehmen als Wert des NetworkSiteID1-Parameters und die ITSP-Netzwerk Website als Wert des NetworkSiteID2-Parameters. Ausführliche Informationen finden Sie unter Erstellen von Netzwerk-standortübergreifenden [Richtlinien in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) in der Bereitstellungsdokumentation und [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps).

3. Rufen Sie die IP-Adresse des SCB-medienendpunkt (Session Border Controller) von Ihrem ITSP. Fügen Sie diese IP-Adresse mit der Subnetzmaske 32 zu dem Netzwerkstandort hinzu, der den Anbieter von Internettelefoniediensten repräsentiert. Ausführliche Informationen finden Sie unter [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).

## <a name="call-admission-control-with-a-third-party-pstn-gateway-or-pbx"></a>Anrufsteuerung mit einem PSTN-Gateway oder einer Nebenstellenanlage eines Drittanbieters

In diesem Thema werden Beispiele für die Bereitstellung der Anrufannahme Steuerung (CAC) für den Link zwischen der Gateway-Schnittstelle des Vermittlungsservers und einem PSTN-Gateway (Public Switched Telephone Network) oder einer PBX (Private Branch Exchange) beschrieben.

### <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a>Fall 1: Anrufsteuerung zwischen dem Vermittlungsserver und einem PSTN-Gateway

CAC kann auf der WAN-Verbindung vom Gateway-Interface des Mediation-Servers zu einer PBX-Anlage oder einem PSTN-Gateway eines Drittanbieters bereitgestellt werden.

**Fall 1: Anrufsteuerung zwischen dem Vermittlungsserver und einem PSTN-Gateway**

![Fall 1: Anrufsteuerung zwischen dem Vermittlungsserver und einem PSTN-Gateway](../../media/CAC_gateways_1.jpg)

In diesem Beispiel wird CAC zwischen dem Vermittlungs Server und einem PSTN-Gateway angewendet. Wenn ein Skype for Business-Clientbenutzer am Netzwerkstandort 1 einen PSTN-Anruf über das PSTN-Gateway in Network Site 2 ablegt, fließt das Medium über die WAN-Verbindung. Für jede PSTN-Sitzung werden daher zwei Prüfungen in Bezug auf die Anrufsteuerung durchgeführt:

- Zwischen der Skype for Business-Clientanwendung und dem Vermittlungs Server

- Zwischen dem Vermittlungs Server und dem PSTN-Gateway

Dies gilt sowohl für eingehende PSTN-Anrufe an einen Client an Netzwerkstandort 1 als auch für ausgehende PSTN-Anrufe, die von einer Clientanwendung an Netzwerkstandort 1 aus getätigt werden.

> [!NOTE]
> Stellen Sie sicher, dass das IP-Subnetz, dem das PSTN-Gateway angehört, konfiguriert und Netzwerkstandort 2 zugeordnet ist.

> [!NOTE]
> Stellen Sie sicher, dass das IP-Subnetz, zu dem beide Schnittstellen des Vermittlungsservers gehören, konfiguriert ist und dem Netzwerkstandort 1 zugeordnet ist.

> [!NOTE]
> Ausführliche Informationen finden Sie unter [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).

### <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a>Fall 2: CAC zwischen dem Vermittlungs Server und einer Drittanbieter-Telefonanlage mit medienendpunkt

Diese Konfiguration ähnelt Fall 1. In beiden Fällen weiß der Vermittlungsserver, welches Gerät Medien am gegenüberliegenden Ende der WAN-Verbindung beendet, und die IP-Adresse des PSTN-Gateways oder der Telefonanlage mit Media Termination Point (MTP) wird auf dem Vermittlungsserver als nächster Hop konfiguriert.

**Fall 2: Anrufsteuerung zwischen dem Vermittlungsserver und einer Drittanbieter-Nebenstellenanlage mit Medienendpunkt**

![Fall 2: Anrufsteuerung zwischen dem Vermittlungsserver und einer Festnetztelefonanlage mit MTP](../../media/CAC_gateways_2.jpg)

In diesem Beispiel wird CAC zwischen dem Vermittlungs Server und der PBX/MTP angewendet. Wenn ein Skype for Business-Clientbenutzer am Netzwerkstandort 1 einen PSTN-Anruf über die Telefonanlage/MTP in Network Site 2 ablegt, fließt das Medium über die WAN-Verbindung. Für jede PSTN-Sitzung werden daher zwei Prüfungen der Anrufsteuerung durchgeführt:

- Zwischen der Skype for Business-Clientanwendung und dem Vermittlungs Server

- Zwischen dem Vermittlungs Server und der PBX/MTP

Dies gilt sowohl für eingehende PSTN-Anrufe an einen Client an Netzwerkstandort 1 als auch für ausgehende PSTN-Anrufe, die von einem Client an Netzwerkstandort 1 aus getätigt werden.

> [!NOTE]
> Stellen Sie sicher, dass das IP-Subnetz, dem der Medienendpunkt angehört, konfiguriert und Netzwerkstandort 2 zugeordnet ist.

> [!NOTE]
> Stellen Sie sicher, dass das IP-Subnetz, zu dem beide Schnittstellen des Vermittlungsservers gehören, konfiguriert ist und dem Netzwerkstandort 1 zugeordnet ist.

> [!NOTE]
> Ausführliche Informationen finden Sie unter [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).

### <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a>Fall 3: CAC zwischen dem Vermittlungs Server und einer Drittanbieter-Telefonanlage ohne medienendpunkt

Fall 3 unterscheidet sich leicht von den ersten beiden Fällen. Wenn kein MTP auf der Drittanbieter-Telefonanlage vorhanden ist, kann der Vermittlungs Server für eine ausgehende Sitzungs Anfrage an die Drittanbieter-PBX-Anlage nicht wissen, wo Medien in der PBX-Grenze beendet werden. In diesem Fall fließt das Medium direkt zwischen dem Vermittlungs Server und dem Endpunktgerät eines Drittanbieters.

**Fall 3: Anrufsteuerung zwischen dem Vermittlungsserver und einer Drittanbieter-Nebenstellenanlage ohne Medienendpunkt**

![Fall 3: Anrufsteuerung zwischen dem Vermittlungsserver und einer Festnetztelefonanlage ohne MTP](../../media/CAC_gateways_3.jpg)

Wenn in diesem Beispiel ein Skype for Business-Clientbenutzer am Netzwerkstandort 1 einen Benutzer über die Telefonanlage anruft, kann der Vermittlungsserver CAC-Prüfungen nur auf dem Proxy-Leg durchführen (zwischen der Skype for Business-Clientanwendung und dem Vermittlungsserver). Da der Vermittlungsserver keine Informationen über das Endpunktgerät aufweist, während die Sitzung angefordert wird, können keine CAC-Prüfungen für die WAN-Verbindung (zwischen dem Vermittlungsserver und dem Endpunkt des Drittanbieters) vor der Einrichtung des Anrufs durchgeführt werden. Nach dem Einrichten der Sitzung vereinfacht der Vermittlungs Server jedoch die Berechnung der im trunk verwendeten Bandbreite.

Bei Anrufen, die vom Endpunkt eines Drittanbieters stammen, sind die Informationen zu diesem Endpunktgerät zum Zeitpunkt der Sitzungsanforderung verfügbar, und die CAC-Prüfung kann sowohl auf den Seiten des Vermittlungsservers ausgeführt werden.

> [!NOTE]
> Stellen Sie sicher, dass das IP-Subnetz, dem die Endpunktgeräte angehören, konfiguriert und Netzwerkstandort 2 zugeordnet ist.

> [!NOTE]
> Stellen Sie sicher, dass das IP-Subnetz, zu dem beide Schnittstellen des Vermittlungsservers gehören, konfiguriert ist und dem Netzwerkstandort 1 zugeordnet ist.

> [!NOTE]
> Ausführliche Informationen finden Sie unter [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).


