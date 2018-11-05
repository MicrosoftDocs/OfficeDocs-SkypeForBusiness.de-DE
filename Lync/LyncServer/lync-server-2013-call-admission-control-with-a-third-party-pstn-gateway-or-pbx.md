---
title: 'Lync Server 2013: Anrufsteuerung mit einem PSTN-Gateway oder einer Nebenstellenanlage eines Drittanbieters'
TOCTitle: Anrufsteuerung mit einem PSTN-Gateway oder einer Nebenstellenanlage eines Drittanbieters
ms:assetid: 95dc4ceb-bcad-48ee-86ec-af911727f853
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398762(v=OCS.15)
ms:contentKeyID: 49294807
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anrufsteuerung mit einem PSTN-Gateway oder einer Nebenstellenanlage eines Drittanbieters in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-20_

In diesem Thema werden Beispiele für die Bereitstellung der Anrufsteuerung (Call Admission Control, CAC) auf der Verbindung zwischen der Gatewayschnittstelle des Vermittlungsservers und einem Drittanbieter-PSTN-Gateway (Public Switched Telephone Network) oder einer Festnetztelefonanlage beschrieben.

## Fall 1: Anrufsteuerung zwischen dem Vermittlungsserver und einem PSTN-Gateway

Die Anrufsteuerung kann auf der WAN-Verbindung von der Gatewayschnittstelle des Vermittlungsservers zu einer Drittanbieter-Nebenstellenanlage oder einem PSTN-Gateway bereitgestellt werden.

**Fall 1: Anrufsteuerung zwischen dem Vermittlungsserver und einem PSTN-Gateway**

![Fall 1: Anrufsteuerung zwischen dem Vermittlungsserver und einem PSTN-Gateway](images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "Fall 1: Anrufsteuerung zwischen dem Vermittlungsserver und einem PSTN-Gateway")

In diesem Beispiel wird die Anrufsteuerung zwischen dem Vermittlungsserver und einem PSTN-Gateway angewendet. Wenn ein Lync-Clientbenutzer an Netzwerkstandort 1 einen PSTN-Anruf über das PSTN-Gateway an Netzwerkstandort 2 tätigt, fließen die Medien durch die WAN-Leitung. Für jede PSTN-Sitzung werden daher zwei Prüfungen in Bezug auf die Anrufsteuerung durchgeführt:

  - Zwischen der Lync-Clientanwendung und dem Vermittlungsserver

  - Zwischen dem Vermittlungsserver und dem PSTN-Gateway

Dies gilt sowohl für eingehende PSTN-Anrufe an einen Client an Netzwerkstandort 1 als auch für ausgehende PSTN-Anrufe, die von einer Clientanwendung an Netzwerkstandort 1 aus getätigt werden.


> [!NOTE]
> Stellen Sie sicher, dass das IP-Subnetz, dem das PSTN-Gateway angehört, konfiguriert und Netzwerkstandort 2 zugeordnet ist.<BR>Stellen Sie sicher, dass das IP-Subnetz, dem beide Schnittstellen des Vermittlungsservers angehören, konfiguriert und Netzwerkstandort 1 zugeordnet ist.<BR>Ausführliche Informationen finden Sie unter <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Zuordnen eines Subnetzes zu einem Netzwerkstandort in Lync Server 2013</A>.



## Fall 2: Anrufsteuerung zwischen dem Vermittlungsserver und einer Drittanbieter-Nebenstellenanlage mit Medienendpunkt

Diese Konfiguration ähnelt Fall 1. In beiden Fällen kennt der Vermittlungsserver das Gerät, das Medien am anderen Ende der WAN-Leitung abschließt, und die IP-Adresse des PSTN-Gateways oder der Nebenstellenanlage mit Medienendpunkt (Media Termination Point, MTP) ist als nächster Hop auf dem Vermittlungsserver konfiguriert.

**Fall 2: Anrufsteuerung zwischen dem Vermittlungsserver und einer Drittanbieter-Nebenstellenanlage mit Medienendpunkt**

![Fall 2: Anrufsteuerung zwischen dem Vermittlungsserver und einer Festnetztelefonanlage mit MTP](images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "Fall 2: Anrufsteuerung zwischen dem Vermittlungsserver und einer Festnetztelefonanlage mit MTP")

In diesem Beispiel wird die Anrufsteuerung zwischen dem Vermittlungsserver und der Nebenstellenanlage/dem Medienendpunkt angewendet. Wenn ein Lync-Clientbenutzer an Netzwerkstandort 1 einen PSTN-Anruf über die Nebenstellenanlage/den Medienendpunkt an Netzwerkstandort 2 tätigt, fließen die Medien durch die WAN-Leitung. Für jede PSTN-Sitzung werden daher zwei Prüfungen in Bezug auf die Anrufsteuerung durchgeführt:

  - Zwischen der Lync-Clientanwendung und dem Vermittlungsserver

  - Zwischen dem Vermittlungsserver und der Nebenstellenanlage/dem Medienendpunkt

Dies gilt sowohl für eingehende PSTN-Anrufe an einen Client an Netzwerkstandort 1 als auch für ausgehende PSTN-Anrufe, die von einem Client an Netzwerkstandort 1 aus getätigt werden.


> [!NOTE]
> Stellen Sie sicher, dass das IP-Subnetz, dem der Medienendpunkt angehört, konfiguriert und Netzwerkstandort 2 zugeordnet ist.<BR>Stellen Sie sicher, dass das IP-Subnetz, dem beide Schnittstellen des Vermittlungsservers angehören, konfiguriert und Netzwerkstandort 1 zugeordnet ist.<BR>Ausführliche Informationen finden Sie unter <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Zuordnen eines Subnetzes zu einem Netzwerkstandort in Lync Server 2013</A>.



## Fall 3: Anrufsteuerung zwischen dem Vermittlungsserver und einer Drittanbieter-Nebenstellenanlage ohne Medienendpunkt

Fall 3 unterscheidet sich leicht von den ersten beiden Fällen. Wenn die Drittanbieter-Nebenstellenanlage keinen Medienendpunkt aufweist, kann der Vermittlungsserver bei einer ausgehenden Sitzungsanforderung an die Drittanbieter-Nebenstellenanlage nicht ermitteln, wo Mediendaten innerhalb des Nebenstellensystems terminiert werden. In diesem Fall fließen die Medien direkt zwischen dem Vermittlungsserver und dem Drittanbieter-Endpunktgerät.

**Fall 3: Anrufsteuerung zwischen dem Vermittlungsserver und einer Drittanbieter-Nebenstellenanlage ohne Medienendpunkt**

![Fall 3: Anrufsteuerung zwischen dem Vermittlungsserver und einer Festnetztelefonanlage ohne MTP](images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "Fall 3: Anrufsteuerung zwischen dem Vermittlungsserver und einer Festnetztelefonanlage ohne MTP")

Wenn ein Lync-Clientbenutzer an Netzwerkstandort 1 einen Anruf an einen Benutzer über die Nebenstellenanlage tätigt, kann der Vermittlungsserver in diesem Beispiel werden Prüfungen in Bezug auf die Anrufsteuerung nur im Proxysegment (zwischen der Lync-Clientanwendung und dem Vermittlungsserver) durchführen. Da der Vermittlungsserver während der Sitzungsanforderung keine Informationen über das Endpunktgerät besitzt, können für die WAN-Verbindung vor Herstellung des Anrufs keine Prüfungen in Bezug auf die Anrufsteuerung durchgeführt werden (zwischen dem Vermittlungsserver und dem Drittanbieter-Endpunkt). Nach dem Einrichten der Sitzung erleichtert der Vermittlungsserver jedoch die Bereitstellung der für den Trunk verwendeten Bandbreite.

Für Anrufe, die vom Drittanbieter-Endpunkt ausgehen, stehen die Informationen über dieses Endpunktgerät zum Zeitpunkt der Sitzungsanforderung zur Verfügung, und Prüfungen in Bezug auf die Anrufsteuerung können auf beiden Seiten des Vermittlungsservers durchgeführt werden.


> [!NOTE]
> Stellen Sie sicher, dass das IP-Subnetz, dem die Endpunktgeräte angehören, konfiguriert und Netzwerkstandort 2 zugeordnet ist.<BR>Stellen Sie sicher, dass das IP-Subnetz, dem beide Schnittstellen des Vermittlungsservers angehören, konfiguriert und Netzwerkstandort 1 zugeordnet ist.<BR>Ausführliche Informationen finden Sie unter <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Zuordnen eines Subnetzes zu einem Netzwerkstandort in Lync Server 2013</A>.


