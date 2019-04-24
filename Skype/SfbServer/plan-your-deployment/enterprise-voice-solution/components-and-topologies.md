---
title: Komponenten und Topologien für die anrufsteuerung in Skype für Unternehmen
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
description: Planung für die anrufsteuerung (CAC), wenn Sie einem MPLS-Netzwerk, einen SIP-Trunk oder ein Drittanbieter-PSTN-Gateway oder einer Nebenstellenanlage verfügen. Gilt für Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: 7022ade98dbd614023a4faaea283b939fa658e73
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32207952"
---
# <a name="components-and-topologies-for-call-admission-control-in-skype-for-business"></a>Komponenten und Topologien für die anrufsteuerung in Skype für Unternehmen

Planung für die anrufsteuerung (CAC), wenn Sie einem MPLS-Netzwerk, einen SIP-Trunk oder ein Drittanbieter-PSTN-Gateway oder einer Nebenstellenanlage verfügen. Gilt für Skype für Business Server Enterprise-VoIP.

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

2. Erstellen Sie eine standortübergreifende Verbindung für den SIP-Trunk mit den entsprechenden Parameterwerten für die Website, die Sie in Schritt 1 erstellt haben. Verwenden Sie beispielsweise den Namen des den Netzwerkstandort in Ihrem Unternehmen als Wert des Parameters NetworkSiteID1 und den Netzwerkstandort ITSP als Wert des Parameters NetworkSiteID2. Weitere Informationen hierzu finden Sie unter [Erstellen von standortübergreifenden Netzwerkrichtlinien in Skype für Business Server](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) in der Dokumentation zur Bereitstellung und [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps).

3. Die IP-Adresse von der Controller des (SCB) Medienendpunkt aus Ihrem ITSP. Fügen Sie diese IP-Adresse mit der Subnetzmaske 32 zu dem Netzwerkstandort hinzu, der den Anbieter von Internettelefoniediensten repräsentiert. Ausführliche Informationen finden Sie unter [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).

## <a name="call-admission-control-with-a-third-party-pstn-gateway-or-pbx"></a>Anrufsteuerung mit einem PSTN-Gateway oder einer Nebenstellenanlage eines Drittanbieters

In diesem Thema wird beschrieben, Beispiele, wie die anrufsteuerung (CAC) auf den Link zwischen Gatewayschnittstelle des Vermittlungsservers und einem Gateway Drittanbieter-public switched Telephone Network (Telefonfestnetz PSTN) oder private Branch Exchange, (Nebenstellenanlage PBX) bereitgestellt werden kann.

### <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a>Fall 1: Anrufsteuerung zwischen dem Vermittlungsserver und einem PSTN-Gateway

CAC bereitgestellt werden kann, über die WAN-Verbindung von der Gatewayschnittstelle des Vermittlungsservers mit einem Drittanbieter-PBX- oder PSTN-Gateway.

**Fall 1: Anrufsteuerung zwischen dem Vermittlungsserver und einem PSTN-Gateway**

![Fall 1: Anrufsteuerung zwischen dem Vermittlungsserver und einem PSTN-Gateway](../../media/CAC_gateways_1.jpg)

In diesem Beispiel wird die Anrufsteuerung zwischen dem Vermittlungsserver und ein PSTN-Gateway angewendet. Wenn eine Skype Business-Client-Benutzers an Netzwerkstandort 1 einen PSTN-Anruf über das PSTN-Gateway in Netzwerkstandort 2 platziert, werden über die WAN-Verbindung das Medium übertragen. Für jede PSTN-Sitzung werden daher zwei Prüfungen in Bezug auf die Anrufsteuerung durchgeführt:

- Zwischen dem Skype für Business-Clientanwendung und dem Vermittlungsserver

- Zwischen dem Vermittlungsserver und PSTN-gateway

Dies gilt sowohl für eingehende PSTN-Anrufe an einen Client an Netzwerkstandort 1 als auch für ausgehende PSTN-Anrufe, die von einer Clientanwendung an Netzwerkstandort 1 aus getätigt werden.

> [!NOTE]
> Stellen Sie sicher, dass das IP-Subnetz, dem das PSTN-Gateway angehört, konfiguriert und Netzwerkstandort 2 zugeordnet ist.

> [!NOTE]
> Stellen Sie sicher, dass das IP-Subnetz, dem beide Schnittstellen des Vermittlungsservers angehören, konfiguriert und Netzwerkstandort 1 zugeordnet.

> [!NOTE]
> Ausführliche Informationen finden Sie unter [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).

### <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a>Fall 2: Anrufsteuerung zwischen dem Vermittlungsserver und einer Drittanbieter-Nebenstellenanlage mit Medienendpunkt

Diese Konfiguration ähnelt Fall 1. In beiden Fällen der Vermittlungsserver weiß, welches Gerät auf dem Installationsdatenträger unter entgegengesetzten Ende der WAN-Verbindung beendet und die IP-Adresse des PSTN-Gateway oder der Nebenstellenanlage mit Media Beendigung Point (MTP) auf dem Vermittlungsserver als Nächster Hop konfiguriert ist.

**Fall 2: Anrufsteuerung zwischen dem Vermittlungsserver und einer Drittanbieter-Nebenstellenanlage mit Medienendpunkt**

![Fall 2: Anrufsteuerung zwischen dem Vermittlungsserver und einer Festnetztelefonanlage mit MTP](../../media/CAC_gateways_2.jpg)

In diesem Beispiel wird die Anrufsteuerung zwischen dem Vermittlungsserver und der Nebenstellenanlage/dem Medienendpunkt angewendet. Wenn eine Skype Business-Client-Benutzers an den Netzwerkstandort 1 einen PSTN-Anruf über die Nebenstellenanlage/MTP befindet sich im Netzwerkstandort 2 tätigt, werden die Medien über die WAN-Verbindung übertragen. Für jede PSTN-Sitzung werden daher zwei Prüfungen der Anrufsteuerung durchgeführt:

- Zwischen dem Skype für Business-Clientanwendung und dem Vermittlungsserver

- Zwischen dem Vermittlungsserver und der Nebenstellenanlage/dem Medienendpunkt

Dies gilt sowohl für eingehende PSTN-Anrufe an einen Client an Netzwerkstandort 1 als auch für ausgehende PSTN-Anrufe, die von einem Client an Netzwerkstandort 1 aus getätigt werden.

> [!NOTE]
> Stellen Sie sicher, dass das IP-Subnetz, dem der Medienendpunkt angehört, konfiguriert und Netzwerkstandort 2 zugeordnet ist.

> [!NOTE]
> Stellen Sie sicher, dass das IP-Subnetz, dem beide Schnittstellen des Vermittlungsservers angehören, konfiguriert und Netzwerkstandort 1 zugeordnet.

> [!NOTE]
> Ausführliche Informationen finden Sie unter [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).

### <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a>Fall 3: Anrufsteuerung zwischen dem Vermittlungsserver und einer Drittanbieter-Nebenstellenanlage ohne Medienendpunkt

Fall 3 unterscheidet sich leicht von den ersten beiden Fällen. Wenn in der Drittanbieter-Nebenstellenanlage ohne MTP vorhanden ist, für eine ausgehende Sitzung weiß Anforderung an die Drittanbieter-Nebenstellenanlage des Vermittlungsservers nicht, in dem Medien in die Nebenstellenanlage Grenze beendet wird. In diesem Fall fließt Mediums direkt zwischen dem Vermittlungsserver und das Gerät Drittanbieter-Endpunkt.

**Fall 3: Anrufsteuerung zwischen dem Vermittlungsserver und einer Drittanbieter-Nebenstellenanlage ohne Medienendpunkt**

![Fall 3: Anrufsteuerung zwischen dem Vermittlungsserver und einer Festnetztelefonanlage ohne MTP](../../media/CAC_gateways_3.jpg)

In diesem Beispiel wird ist eine Skype Business-Client-Benutzers an Netzwerkstandort 1 einen Anruf an einen Benutzer über die Nebenstellenanlage platziert der Vermittlungsserver CAC Überprüfungen nur auf Proxy vom Abschnitt zwischen dem (der Skype für Business-Clientanwendung) und Mediation Server ausführen. Da der Vermittlungsserver keinen Informationen zu dem Endgerät während die Sitzung angefordert wird, können nicht CAC Überprüfungen ausgeführt werden, über die WAN-Link (zwischen dem Vermittlungsserver und dem Drittanbieter-Endpunkt) vor dem Herstellen der Verbindung. Nachdem die Sitzung eingerichtet ist, jedoch erleichtert der Vermittlungsserver in der Buchhaltung für die auf dem Trunk verwendete Bandbreite.

Für Anrufe, die vom Endpunkt von Drittanbietern stammen, die Informationen zu diesem Gerät Endpunkt ist zum Zeitpunkt der sitzungsanforderung und CAC Kontrollkästchen auf beiden Seiten des Vermittlungsservers durchgeführt werden kann.

> [!NOTE]
> Stellen Sie sicher, dass das IP-Subnetz, dem die Endpunktgeräte angehören, konfiguriert und Netzwerkstandort 2 zugeordnet ist.

> [!NOTE]
> Stellen Sie sicher, dass das IP-Subnetz, dem beide Schnittstellen des Vermittlungsservers angehören, konfiguriert und Netzwerkstandort 1 zugeordnet.

> [!NOTE]
> Ausführliche Informationen finden Sie unter [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).


