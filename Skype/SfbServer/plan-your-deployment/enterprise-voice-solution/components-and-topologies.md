---
title: Komponenten und Topologien für die Anrufsteuerung in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
description: Planen der Anrufsteuerung, wenn Sie über ein MPLS-Netzwerk, einen SIP-Trunk oder ein Drittanbieter-PSTN-Gateway oder eine Nebenstellenanlage verfügen. Gilt für Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: e40525121020259a40f10d90cd79d70aaa749ac3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825845"
---
# <a name="components-and-topologies-for-call-admission-control-in-skype-for-business"></a>Komponenten und Topologien für die Anrufsteuerung in Skype for Business

Planen der Anrufsteuerung, wenn Sie über ein MPLS-Netzwerk, einen SIP-Trunk oder ein Drittanbieter-PSTN-Gateway oder eine Nebenstellenanlage verfügen. Gilt für Skype for Business Server Enterprise-VoIP.

Die Themen in diesem Abschnitt liefern Informationen zu speziellen Faktoren, die bei der Bereitstellung der Anrufsteuerung mit verschiedenen Typen von Netzwerktopologien berücksichtigt werden sollten.

## <a name="call-admission-control-on-an-mpls-network"></a>Anrufsteuerung in einem MPLS-Netzwerk

In einem MPLS-Netzwerk (Multiprotocol Label Switching) sind alle Standorte vollständig miteinander vernetzt, d. h. alle Standorte sind direkt mit dem MPLS-Backbone des Internetdienstanbieters verbunden, und jedem Standort wird Bandbreite für eine WAN-Verbindung mit der MPLS-Cloud zur Verfügung gestellt. Es ist kein Netzwerkhub oder zentraler Standort zur Steuerung des IP-Routings vorhanden. Die folgende Abbildung zeigt ein einfaches Beispiel für ein auf der MPLS-Technologie basierendes Netzwerk.

**Beispiel eines MPLS-Netzwerks**

![CAC with MPLS](../../media/CAC_MPLS_1.jpg)

Zur Bereitstellung der Anrufsteuerung (Call Admission Control, CAC) in einem MPLS-Netzwerk erstellen Sie eine Netzwerkregion für die MPLS-Cloud und Netzwerkstandorte für jeden MPLS-Zweigstellenstandort. Die folgende Abbildung zeigt, wie Netzwerkregion und Netzwerkstandorte konfiguriert sein sollten, um das MPLS-Beispielnetzwerk aus der oben stehenden Abbildung darzustellen. Die Bandbreitenbeschränkungen insgesamt sowie die Bandbreitenbeschränkung pro Sitzung basieren auf der Kapazität der WAN-Verbindung zwischen jedem Netzwerkstandort und der Netzwerkregion, welche die MPLS-Cloud darstellt.

**Netzwerkregion und Netzwerkstandorte für ein MPLS-Netzwerk**

![Anrufsteuerung (Call Admission Control, CAC) mit einem MPLS-Diagramm](../../media/CAC_MPLS_2.jpg)

## <a name="call-admission-control-on-a-sip-trunk"></a>Anrufsteuerung für einen SIP-Trunk

Zur Bereitstellung der Anrufsteuerung für einen SIP-Trunk erstellen Sie einen Netzwerkstandort, der den Anbieter von Internettelefoniediensten repräsentiert. Um Bandbreitenrichtlinienwerte auf den SIP-Trunk anzuwenden, erstellen Sie eine standortübergreifende Richtlinie zwischen dem Netzwerkstandort in Ihrem Unternehmen und dem Netzwerkstandort, der für den Anbieter von Internettelefoniediensten erstellt wird.

Die folgende Abbildung zeigt ein Beispiel für die Bereitstellung der Anrufsteuerung für einen SIP-Trunk.

**Konfiguration der Anrufsteuerung für einen SIP-Trunk**

![Diagramm für das Sip-Trunking-Anrufsteuerungs-SIP-Trunking](../../media/CAC_SIP_trunk_1.jpg)

Zur Konfiguration der Anrufsteuerung für einen SIP-Trunk müssen Sie während der Bereitstellung der Anrufsteuerung die folgenden Aufgaben ausführen:

1. Erstellen eines Netzwerkstandorts, der den Anbieter von Internettelefoniediensten repräsentiert. Zuordnen des Netzwerkstandorts zu einer geeigneten Netzwerkregion und Zuweisen eines Bandbreitenwerts von Null für Audio und Video für diesen Netzwerkstandort. Ausführliche Informationen finden Sie unter [Configure Network Sites for CAC](https://technet.microsoft.com/library/afcea38f-5789-45ec-97af-c6e38364950c.aspx) in der Bereitstellungsdokumentation.

    > [!NOTE]
    > Für den Anbieter von Internettelefoniediensten ist diese Netzwerkstandortkonfiguration nicht funktionsfähig. Die Bandbreitenrichtlinienwerte werden tatsächlich in Schritt 2 angewendet.

2. Erstellen Sie eine standortübergreifende Verbindung für den SIP-Trunk unter Verwendung der relevanten Parameterwerte für den in Schritt 1 erstellten Standort. Verwenden Sie z. B. den Namen des Netzwerkstandorts in Ihrem Unternehmen als Wert des Parameters "NetworkSiteID1" und den ITSP-Netzwerkstandort als Wert des Parameters "NetworkSiteID2". Ausführliche Informationen finden Sie unter "Erstellen von standortübergreifenden Netzwerkrichtlinien [in Skype for Business Server"](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) in der Bereitstellungsdokumentation und unter ["New-CsNetworkInterSitePolicy".](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)

3. Erhalten Sie die IP-Adresse des Medienendpunkts des Session Border Controllers (SCB) von Ihrem ITSP. Fügen Sie diese IP-Adresse mit der Subnetzmaske 32 zu dem Netzwerkstandort hinzu, der den Anbieter von Internettelefoniediensten repräsentiert. Ausführliche Informationen finden Sie unter [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).

## <a name="call-admission-control-with-a-third-party-pstn-gateway-or-pbx"></a>Anrufsteuerung mit einem Drittanbieter-PSTN-Gateway oder einer Nebenstellenanlage

In diesem Thema werden Beispiele für die Bereitstellung der Anrufsteuerung (Call Admission Control, CAC) für die Verbindung zwischen der Gatewayschnittstelle des Vermittlungsservers und einem PstN-Gateway (Public Switched Telephone Network) eines Drittanbieters oder einer Nebenstellenanlage (Private Branch Exchange, PBX) beschrieben.

### <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a>Fall 1: Anrufsteuerung zwischen dem Vermittlungsserver und einem PSTN-Gateway

Die Cac kann auf der WAN-Verbindung von der Gatewayschnittstelle des Vermittlungsservers zu einer Nebenstellenanlage oder einem PstN-Gateway eines Drittanbieters bereitgestellt werden.

**Fall 1: Anrufsteuerung zwischen dem Vermittlungsserver und einem PSTN-Gateway**

![Fall 1: Cac between Mediation Server PSTN Gateway](../../media/CAC_gateways_1.jpg)

In diesem Beispiel wird die Anrufsteuerung zwischen dem Vermittlungsserver und einem PSTN-Gateway angewendet. Wenn ein Skype for Business-Clientbenutzer an Netzwerkstandort 1 einen Festnetzanruf über das PstN-Gateway an Netzwerkstandort 2 abstelle, fließen die Medien über die WAN-Verbindung. Für jede PSTN-Sitzung werden daher zwei Prüfungen in Bezug auf die Anrufsteuerung durchgeführt:

- Zwischen der Skype for Business-Clientanwendung und dem Vermittlungsserver

- Zwischen dem Vermittlungsserver und dem PSTN-Gateway

Dies gilt sowohl für eingehende PSTN-Anrufe an einen Client an Netzwerkstandort 1 als auch für ausgehende PSTN-Anrufe, die von einer Clientanwendung an Netzwerkstandort 1 aus getätigt werden.

> [!NOTE]
> Stellen Sie sicher, dass das IP-Subnetz, dem das PSTN-Gateway angehört, konfiguriert und Netzwerkstandort 2 zugeordnet ist.

> [!NOTE]
> Stellen Sie sicher, dass das IP-Subnetz, dem beide Schnittstellen des Vermittlungsservers angehören, konfiguriert und Netzwerkstandort 1 zugeordnet ist.

> [!NOTE]
> Ausführliche Informationen finden Sie unter [Zuordnen eines Subnetzes zu einem Netzwerkstandort](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).

### <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a>Fall 2: Anrufsteuerung zwischen dem Vermittlungsserver und einer Drittanbieter-Nebenstellenanlage mit Medienendpunkt

Diese Konfiguration ähnelt Fall 1. In beiden Fällen kennt der Vermittlungsserver das Gerät, das Medien am anderen Ende der WAN-Leitung abschließt, und die IP-Adresse des PSTN-Gateways oder der Nebenstellenanlage mit Medienendpunkt (Media Termination Point, MTP) ist als nächster Hop auf dem Vermittlungsserver konfiguriert.

**Fall 2: Anrufsteuerung zwischen dem Vermittlungsserver und einer Drittanbieter-Nebenstellenanlage mit Medienendpunkt**

![Fall 2: Cac between Mediation Server PBX with MTP](../../media/CAC_gateways_2.jpg)

In diesem Beispiel wird die Anrufsteuerung zwischen dem Vermittlungsserver und der Nebenstellenanlage/dem Medienendpunkt angewendet. Wenn ein Skype for Business-Clientbenutzer am Netzwerkstandort 1 einen Festnetzanruf über die Nebenstellenanlage/den Medienendpunkt an Netzwerkstandort 2 abstelle, fließen die Medien über die WAN-Verbindung. Für jede PSTN-Sitzung werden daher zwei Prüfungen in Bezug auf die Anrufsteuerung durchgeführt:

- Zwischen der Skype for Business-Clientanwendung und dem Vermittlungsserver

- Zwischen dem Vermittlungsserver und der Nebenstellenanlage/dem Medienendpunkt

Dies gilt sowohl für eingehende PSTN-Anrufe an einen Client an Netzwerkstandort 1 als auch für ausgehende PSTN-Anrufe, die von einem Client an Netzwerkstandort 1 aus getätigt werden.

> [!NOTE]
> Stellen Sie sicher, dass das IP-Subnetz, dem der Medienendpunkt angehört, konfiguriert und Netzwerkstandort 2 zugeordnet ist.

> [!NOTE]
> Stellen Sie sicher, dass das IP-Subnetz, dem beide Schnittstellen des Vermittlungsservers angehören, konfiguriert und Netzwerkstandort 1 zugeordnet ist.

> [!NOTE]
> Ausführliche Informationen finden Sie unter [Zuordnen eines Subnetzes zu einem Netzwerkstandort](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).

### <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a>Fall 3: Anrufsteuerung zwischen dem Vermittlungsserver und einer Drittanbieter-Nebenstellenanlage ohne Medienendpunkt

Fall 3 unterscheidet sich leicht von den ersten beiden Fällen. Wenn die Drittanbieter-Nebenstellenanlage keinen Medienendpunkt aufweist, kann der Vermittlungsserver bei einer ausgehenden Sitzungsanforderung an die Drittanbieter-Nebenstellenanlage nicht ermitteln, wo Mediendaten innerhalb des Nebenstellensystems terminiert werden. In diesem Fall fließen die Medien direkt zwischen dem Vermittlungsserver und dem Drittanbieter-Endpunktgerät.

**Fall 3: Anrufsteuerung zwischen dem Vermittlungsserver und einer Drittanbieter-Nebenstellenanlage ohne Medienendpunkt**

![Fall 3: Cac between Mediation Server PBX no MTP](../../media/CAC_gateways_3.jpg)

Wenn in diesem Beispiel ein Skype for Business-Clientbenutzer an Netzwerkstandort 1 einen Benutzer über die Nebenstellenanlage anruft, kann der Vermittlungsserver Anrufüberprüfungen nur im Proxyabschnitt (zwischen der Skype for Business-Clientanwendung und dem Vermittlungsserver) durchführen. Da der Vermittlungsserver während der Sitzungsanforderung keine Informationen über das Endpunktgerät besitzt, können für die WAN-Verbindung vor Herstellung des Anrufs keine Prüfungen in Bezug auf die Anrufsteuerung durchgeführt werden (zwischen dem Vermittlungsserver und dem Drittanbieter-Endpunkt). Nach dem Einrichten der Sitzung erleichtert der Vermittlungsserver jedoch die Bereitstellung der für den Trunk verwendeten Bandbreite.

Für Anrufe, die vom Drittanbieter-Endpunkt ausgehen, stehen die Informationen über dieses Endpunktgerät zum Zeitpunkt der Sitzungsanforderung zur Verfügung, und Prüfungen in Bezug auf die Anrufsteuerung können auf beiden Seiten des Vermittlungsservers durchgeführt werden.

> [!NOTE]
> Stellen Sie sicher, dass das IP-Subnetz, dem die Endpunktgeräte angehören, konfiguriert und Netzwerkstandort 2 zugeordnet ist.

> [!NOTE]
> Stellen Sie sicher, dass das IP-Subnetz, dem beide Schnittstellen des Vermittlungsservers angehören, konfiguriert und Netzwerkstandort 1 zugeordnet ist.

> [!NOTE]
> Ausführliche Informationen finden Sie unter [Zuordnen eines Subnetzes zu einem Netzwerkstandort](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).


