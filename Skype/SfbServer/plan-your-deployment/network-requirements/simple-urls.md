---
title: DNS-Anforderungen für einfache URLs in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
description: 'Zusammenfassung: Überprüfen Sie die Überlegungen zu einfachen URLs in diesem Thema, bevor Sie DNS-Einträge für Skype for Business Server implementieren.'
ms.openlocfilehash: d638ff2d3d1b89deaad90c054698692e70ffaae7
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60777915"
---
# <a name="dns-requirements-for-simple-urls-in-skype-for-business-server"></a>DNS-Anforderungen für einfache URLs in Skype for Business Server

**Zusammenfassung:** Lesen Sie die Überlegungen zu einfachen URLs in diesem Thema, bevor Sie DNS-Einträge für Skype for Business Server implementieren.

Einfache URLs vereinfachen die Teilnahme an Besprechungen für Ihre Benutzer und erleichtern Administratoren den Zugriff auf Skype for Business Server Verwaltungstools. Einfache URLs verwenden eine eigene Domäne, die keiner der von Ihnen definierten SIP-Domänen entsprechen darf. 

Skype for Business Server unterstützt die folgenden drei einfachen URLs: Besprechung, Einwahl und Administrator. Sie müssen einfache URLs für Besprechungen und Einwahl einrichten, und die einfache ADMINISTRATOR-URL ist optional. Die zur Unterstützung einfacher URLs erforderlichen DNS-Einträge (Domain Name System) richten sich danach, wie Sie die einfachen URLs definiert haben und ob Sie die Notfallwiederherstellung für einfache URLs unterstützen möchten. 

## <a name="simple-url-scope"></a>Einfacher URL-Bereich

Sie können Ihre einfachen URLs auf globaler Ebene konfigurieren oder unterschiedliche einfache URLs für jeden zentralen Standort in Ihrer Organisation angeben. Wenn sowohl eine globale einfache URL als auch eine einfache URL für einen Standort angegeben wird, hat die einfache URL für den Standort Vorrang. 

In den meisten Fällen wird empfohlen, einfache URLs nur auf globaler Ebene festzulegen, damit sich die einfache BESPRECHUNGS-URL eines Benutzers nicht ändert, wenn er von einer Website zu einer anderen wechselt. Eine Ausnahme stellen Organisationen dar, die unterschiedliche Telefonnummern für Einwahlbenutzer an unterschiedlichen Standorten verwenden. Beachten Sie Folgendes: Wenn Sie eine einfache URL (beispielsweise die einfache URL für die Einwahl) als einfache URL auf Standortebene festlegen, müssen Sie auch die weiteren einfachen URLs für diesen Standort auf Standortebene konfigurieren.

Sie können globale einfache URLs im Topologie-Generator festlegen. Verwenden Sie das Cmdlet Set-CsSimpleURLConfiguration, um eine einfache URL auf Websiteebene festzulegen.

Das Definieren einer einfachen URL erfordert auch das Festlegen eines A- und/oder AAAA-Eintrags in Ihrer DNS-Konfiguration.

## <a name="simple-url-naming-and-validation-rules"></a>Benennungs- und Überprüfungsregeln für einfache URLs
<a name="BK_Valid"> </a>

Der Topologie-Generator und die Cmdlets der Skype for Business Server-Verwaltungsshell erzwingen mehrere Überprüfungsregeln für Ihre einfachen URLs. Sie müssen einfache URLs für Besprechungen und Einwahl angeben, die Festlegung einer einfachen Admin-URL ist jedoch optional. Jede SIP-Domäne muss über eine separate einfache URL für Besprechungen (Meet) verfügen, Sie benötigen jedoch nur eine einfache URL für die Einwahl (Dialin) und eine einfache Admin-URL für die gesamte Organisation.

Jede einfache URL in Ihrer Organisation muss einen eindeutigen Namen haben und darf kein Präfix einer anderen einfachen URL sein (Sie konnten z. B. nicht `SfB2015.contoso.com/Meet` als einfache Besprechungs-URL und `SfB2015.contoso.com/Meet/Dialin` als einfache Dialin-URL festlegen). Namen einfacher URLs dürfen nicht den FQDN Eines Ihrer Pools oder Portinformationen enthalten (z. B. https://FQDN:88/meet ist dies nicht zulässig). Alle einfachen URLs müssen mit dem Präfix "https://" beginnen. 

Einfache URLs können ausschließlich alphanumerische Zeichen enthalten – a-z, A-Z, 0-9 und Punkt (.). Wenn Sie andere Zeichen verwenden, funktioniert die einfache URL möglicherweise nicht wie erwartet.

## <a name="changing-simple-urls-after-deployment"></a>Ändern einfacher URLs nach der Bereitstellung
<a name="BK_Valid"> </a>

Wenn Sie eine einfache URL nach der anfänglichen Bereitstellung ändern, müssen Sie sich der Auswirkungen auf DNS-Einträge und Zertifikate für einfache URLs bewusst sein. Wenn die Änderung sich auf die Basis einer einfachen URL auswirkt, müssen Sie auch die DNS-Einträge und Zertifikate ändern. Wenn Sie beispielsweise die `https://SfB2015.contoso.com/Meet` `https://meet.contoso.com` Basis-URL von in `SfB2015.contoso.com` `meet.contoso.com` ändern, müssen Sie die DNS-Einträge und -Zertifikate so ändern, dass sie auf `meet.contoso.com` . Wenn Sie die einfache URL von in geändert `https://SfB2015.contoso.com/Meet` `https://SfB2015.contoso.com/Meetings` haben, bleibt die Basis-URL `SfB2015.contoso.com` unverändert, sodass keine DNS- oder Zertifikatänderungen erforderlich sind.

Wenn Sie jedoch einen einfachen URL-Namen ändern, müssen Sie **Enable-CsComputer** auf jedem Director und Front-End-Server ausführen, um die Änderung zu registrieren.

## <a name="naming-examples-for-simple-urls"></a>Benennungsbeispiele für einfache URLs
<a name="BK_Valid"> </a>

Es gibt drei empfohlene Optionen für die Benennung einfacher URLs. Die Auswahl der Benennungsoption hat Auswirkungen darauf, wie Sie Ihre DNS-A-Einträge und Zertifikate zur Unterstützung einfacher URLs einrichten. Bei jeder Option müssen Sie eine einfache URL für Besprechungen (Meet) für jede SIP-Domäne in Ihrer Organisation konfigurieren. Sie benötigen innerhalb der Organisation immer nur eine einfache URL für die Einwahl (Dial) und eine einfache Admin-URL – unabhängig davon, wie viele SIP-Domänen Sie verwenden. 

Sie benötigen innerhalb der Organisation immer nur eine einfache URL für die Einwahl (Dial) und eine einfache Admin-URL – unabhängig davon, wie viele SIP-Domänen Sie verwenden.

Bei Option 1 erstellen Sie einen neue SIP-Domänennamen für jede einfache URL.

Wenn Sie sich für diese Option entscheiden, benötigen Sie einen separaten DNS-A-Eintrag für jede einfache URL, und jeder einfache Meet-URL muss in Ihren Zertifikaten benannt sein.

**Benennung einfacher URLs – Option 1**


| **Einfache URL** <br/> | **Beispiel** <br/>                                                                                                    |
|:---------------------|:---------------------------------------------------------------------------------------------------------------------|
| Treffen  <br/>          | `https://meet.contoso.com``https://meet.fabrikam.com`usw. (eine für jede SIP-Domäne in Ihrer Organisation)  <br/> |
| Einwahl  <br/>       | `<https://dialin.contoso.com>`  <br/>                                                                                  |
| Administrator  <br/>         | `<https://admin.contoso.com>`  <br/>                                                                                   |

Bei Option 2 basieren einfache URLs auf dem `SfB2015.contoso.com` Domänennamen. Daher benötigen Sie nur einen DNS-A-Eintrag, der alle drei Arten von einfachen URLs unterstützt. Dieser DNS A-Eintrag verweist auf `SfB2015.contoso.com` . Zusätzlich benötigen Sie weiterhin separate DNS-A-Einträge für weitere SIP-Domänen in Ihrer Organisation. 

**Benennung einfacher URLs – Option 2**


| **Einfache URL** <br/> | **Beispiel** <br/>                                                                                                                    |
|:---------------------|:-------------------------------------------------------------------------------------------------------------------------------------|
| Treffen  <br/>          | `https://SfB2015.contoso.com/Meet``https://SfB2015.fabrikam.com/Meet`usw. (eine für jede SIP-Domäne in Ihrer Organisation)  <br/> |
| Einwahl  <br/>       | `<https://SfB2015.contoso.com/Dialin>`  <br/>                                                                                          |
| Administrator  <br/>         | `<https://SfB2015.contoso.com/Admin>`  <br/>                                                                                           |

Option 3 ist sinnvoll, wenn Sie über zahlreiche SIP-Domänen verfügen und diesen separate einfache URLs für Besprechungen (Meet) zuweisen, jedoch die Anzahl von DNS-Einträgen und die Zertifikatanforderungen für diese einfachen URLs minimieren möchten. 

**Benennung einfacher URLs – Option 3**


| **Einfache URL** <br/> | **Beispiel** <br/>                                                                                                      |
|:---------------------|:-----------------------------------------------------------------------------------------------------------------------|
| Treffen  <br/>          | `<https://SfB2015.contoso.com/contosoSIPdomain/Meet>`  <br/> `<https://SfB2015.contoso.com/fabrikamSIPdomain/Meet>`  <br/> |
| Einwahl  <br/>       | `<https://SfB2015.contoso.com/Dialin>`  <br/>                                                                            |
| Administrator  <br/>         | `<https://SfB2015.contoso.com/Admin>`  <br/>                                                                             |

## <a name="disaster-recovery-option-for-simple-urls"></a>Notfallwiederherstellungsoption für einfache URLs
<a name="BK_Valid"> </a>

Wenn Sie über mehrere Standorte verfügen, die Front-End-Pools enthalten, und Ihr DNS-Anbieter GeoDNS unterstützt, können Sie Ihre DNS-Einträge für einfache URLs einrichten, um die Notfallwiederherstellung zu unterstützen, sodass die Funktionalität der einfachen URL auch dann fortgesetzt wird, wenn ein ganzer Front-End-Pool ausfällt. Dieses Feature für die Notfallwiederherstellung unterstützt die einfachen URLs für Besprechungen und Einwahl.

Erstellen Sie zum Konfigurieren dieser Notfallwiederherstellung zwei GeoDNS-Adressen. Jede Adresse hat zwei DNS A- oder CNAME-Einträge. Diese werden in zwei Pools aufgelöst, die zu Notfallwiederherstellungszwecken ein Paar bilden. Eine GeoDNS-Adresse wird für den internen Zugriff verwendet und in den internen Web-FQDN oder die Lastenausgleichs-IP-Adresse für die beiden Pools aufgelöst. Die andere GeoDNS-Adresse wird für den externen Zugriff verwendet und in den externen Web-FQDN oder die Lastenausgleich-IP-Adresse für die beiden Pools aufgelöst. Im Folgenden sehen Sie ein Beispiel für eine einfache URL vom Typ Meet, in dem vollqualifizierte Domänennamen (FQDNs) für die Pools verwendet werden. 

```console
Meet-int.geolb.contoso.com
     Pool1InternalWebFQDN.contoso.com
     Pool2InternalWebFQDN.contoso.com
```

```console
Meet-ext.geolb.contoso.com
     Pool1ExternalWebFQDN.contoso.com
     Pool2ExternalWebFQDN.contoso.com
```

Erstellen Sie dann CNAME-Einträge, die Ihre einfache Meet-URL (z. `meet.contoso.com` B. ) in die beiden GeoDNS-Adressen auflösen.

> [!NOTE]
> Wenn in Ihrem Netzwerk das so genannte Hairpinning eingesetzt wird (der gesamte Datenverkehr der einfachen URL wird über den externen Link geleitet, einschließlich des Datenverkehrs aus der Organisation), können Sie einfach nur die externe GeoDNS-Adresse konfigurieren und Ihre einfache Meet-URL nur in diese externe Adresse auflösen.

Wenn Sie diese Methode verwenden, können Sie jede GeoDNS-Adresse so konfigurieren, dass entweder eine Roundrobin-Methode zur Verteilung der Anforderungen an die beiden Pools verwendet wird oder dass hauptsächlich eine Verbindung mit einem Pool hergestellt wird (z. B. mit dem Pool, der geografisch näher ist) und der andere Pool nur bei einem Konnektivitätsfehler zum Einsatz kommt. 

Sie können dieselbe Konfiguration für die einfache Dialin-URL verwenden. Erstellen Sie hierzu zusätzliche Einträge wie im vorherigen Beispiel, die in  `dialin` `meet` den DNS-Einträgen ersetzen. Verwenden Sie für die einfache Admin-URL eine der weiter oben in diesem Abschnitt aufgelisteten drei Optionen.

Sobald diese Konfiguration eingerichtet ist, müssen Sie eine Überwachungsanwendung verwenden, um die HTTP-Überwachung so einzurichten, dass nach Fehlern Ausschau gehalten wird. Überwachen Sie für den externen Zugriff, um sicherzustellen, dass HTTPS GET lyncdiscover.<sipdomain> Anforderungen an den externen Web-FQDN oder die IP-Adresse des Lastenausgleichs für die beiden Pools sind erfolgreich. Beispielsweise dürfen die folgenden Anforderungen keinen **ACCEPT**-Header enthalten und müssen **200 OK** zurückgegeben.

```console
HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

For internal access, you must monitor port 5061 on the internal web FQDN or load balancer IP address for the two pools. Wenn Verbindungsfehler erkannt werden, muss die VIP für diese Pools die Ports 80, 443 und 4443 schließen.


