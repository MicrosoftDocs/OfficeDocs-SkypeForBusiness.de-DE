---
title: DNS-Anforderungen für einfache URLs in Skype for Business Server
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
ms.assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
description: 'Zusammenfassung: Lesen Sie die Überlegungen zu einfachen URLs in diesem Thema, bevor Sie die DNS-Einträge für Skype for Business Server implementieren.'
ms.openlocfilehash: d1c4213e1fe28c6f42cd4fa14f48bc8ce9b7bdf1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834585"
---
# <a name="dns-requirements-for-simple-urls-in-skype-for-business-server"></a>DNS-Anforderungen für einfache URLs in Skype for Business Server

**Zusammenfassung:** Lesen Sie die Überlegungen zur einfachen URL in diesem Thema, bevor Sie die DNS-Einträge für Skype for Business Server implementieren.

Einfache URLs erleichtern Ihren Benutzern das Beitreten zu Besprechungen und erleichtern Administratoren den Zugriff auf Skype for Business Server-Verwaltungstools. Einfache URLs verwenden eine eigene Domäne, die nicht mit den von Ihnen definierten SIP-Domänen übereinstimmen darf. 

Skype for Business Server unterstützt die folgenden drei einfachen URLs: "Meet", "Dial-In" und "Admin". Sie müssen einfache URLs für "Meet" und "Dial-In" einrichten, und die einfache ADMIN-URL ist optional. Die zur Unterstützung einfacher URLs erforderlichen DNS-Einträge (Domain Name System) richten sich danach, wie Sie die einfachen URLs definiert haben und ob Sie die Notfallwiederherstellung für einfache URLs unterstützen möchten. 

## <a name="simple-url-scope"></a>Bereich für einfache URLs

Sie können Ihre einfachen URLs auf globaler Ebene konfigurieren oder unterschiedliche einfache URLs für jeden zentralen Standort in Ihrer Organisation angeben. Wenn sowohl eine globale einfache URL als auch eine einfache URL für einen Standort angegeben wird, hat die einfache URL für den Standort Vorrang. 

In den meisten Fällen wird empfohlen, dass Sie einfache URLs nur auf globaler Ebene festlegen, damit sich die einfache MEET-URL eines Benutzers nicht ändert, wenn sie von einem Standort an einen anderen wechseln. Eine Ausnahme stellen Organisationen dar, die unterschiedliche Telefonnummern für Einwahlbenutzer an unterschiedlichen Standorten verwenden. Beachten Sie Folgendes: Wenn Sie eine einfache URL (beispielsweise die einfache URL für die Einwahl) als einfache URL auf Standortebene festlegen, müssen Sie auch die weiteren einfachen URLs für diesen Standort auf Standortebene konfigurieren.

Sie können globale einfache URLs im Topologie-Generator festlegen. Verwenden Sie zum Festlegen einer einfachen URL auf Standortebene das Set-CsSimpleURLConfiguration Cmdlet.

Das Definieren einer einfachen URL erfordert auch das Festlegen eines A- und/oder AAAA-Eintrags in Ihrer DNS-Konfiguration.

## <a name="simple-url-naming-and-validation-rules"></a>Benennungs- und Validierungsregeln für einfache URLs
<a name="BK_Valid"> </a>

Der Topologie-Generator und die Skype for Business Server-Verwaltungsshell-Cmdlets erzwingen mehrere Gültigkeitsregeln für Ihre einfachen URLs. Sie müssen einfache URLs für Besprechungen und Einwahl angeben, die Festlegung einer einfachen Admin-URL ist jedoch optional. Jede SIP-Domäne muss über eine separate einfache URL für Besprechungen (Meet) verfügen, Sie benötigen jedoch nur eine einfache URL für die Einwahl (Dialin) und eine einfache Admin-URL für die gesamte Organisation.

Jede einfache URL in Ihrer Organisation muss einen eindeutigen Namen haben und darf kein Präfix einer anderen einfachen URL sein (Sie könnten z. B. SfB2015.contoso.com/Meet nicht als einfache Meet-URL und SfB2015.contoso.com/Meet/Dialin als einfache URL für die Einwahl festlegen). Namen einfacher URLs dürfen nicht den FQDN Ihrer Pools oder Portinformationen enthalten (z. B. https://FQDN:88/meet sind nicht zulässig). Alle einfachen URLs müssen mit dem Präfix "https://" beginnen. 

Einfache URLs können ausschließlich alphanumerische Zeichen enthalten – a-z, A-Z, 0-9 und Punkt (.). Wenn Sie andere Zeichen verwenden, funktioniert die einfache URL möglicherweise nicht wie erwartet.

## <a name="changing-simple-urls-after-deployment"></a>Ändern einfacher URLs nach der Bereitstellung
<a name="BK_Valid"> </a>

Wenn Sie eine einfache URL nach der anfänglichen Bereitstellung ändern, müssen Sie sich der Auswirkungen auf DNS-Einträge und Zertifikate für einfache URLs bewusst sein. Wenn die Änderung sich auf die Basis einer einfachen URL auswirkt, müssen Sie auch die DNS-Einträge und Zertifikate ändern. Wenn Sie z. B. die Basis-URL von SfB2015.contoso.com in meet.contoso.com ändern, müssen Sie die DNS-Einträge und -Zertifikate so ändern, dass sie auf https://SfB2015.contoso.com/Meet https://meet.contoso.com meet.contoso.com. Wenn Sie die einfache URL in geändert haben, bleibt die Basis-URL von SfB2015.contoso.com identisch, sodass keine DNS- oder https://SfB2015.contoso.com/Meet https://SfB2015.contoso.com/Meetings Zertifikatänderungen erforderlich sind.

Wenn Sie jedoch einen Namen für eine einfache URL ändern, müssen Sie **"Enable-CsComputer"** auf jedem Director und Front-End-Server ausführen, um die Änderung zu registrieren.

## <a name="naming-examples-for-simple-urls"></a>Benennungsbeispiele für einfache URLs
<a name="BK_Valid"> </a>

Es gibt drei empfohlene Optionen für die Benennung einfacher URLs. Die Auswahl der Benennungsoption hat Auswirkungen darauf, wie Sie Ihre DNS-A-Einträge und Zertifikate zur Unterstützung einfacher URLs einrichten. Bei jeder Option müssen Sie eine einfache URL für Besprechungen (Meet) für jede SIP-Domäne in Ihrer Organisation konfigurieren. Sie benötigen innerhalb der Organisation immer nur eine einfache URL für die Einwahl (Dial) und eine einfache Admin-URL – unabhängig davon, wie viele SIP-Domänen Sie verwenden. 

Sie benötigen innerhalb der Organisation immer nur eine einfache URL für die Einwahl (Dial) und eine einfache Admin-URL – unabhängig davon, wie viele SIP-Domänen Sie verwenden.

Bei Option 1 erstellen Sie einen neue SIP-Domänennamen für jede einfache URL.

Wenn Sie sich für diese Option entscheiden, benötigen Sie einen separaten DNS-A-Eintrag für jede einfache URL, und jeder einfache Meet-URL muss in Ihren Zertifikaten benannt sein.

**Benennung einfacher URLs – Option 1**


| **Einfache URL** <br/> | **Beispiel** <br/>                                                                                                    |
|:---------------------|:---------------------------------------------------------------------------------------------------------------------|
| Meet  <br/>          | https://meet.contoso.com, https://meet.fabrikam.com und so weiter (eine für jede SIP-Domäne in Ihrer Organisation)  <br/> |
| Einwahl  <br/>       | <https://dialin.contoso.com>  <br/>                                                                                  |
| Admin  <br/>         | <https://admin.contoso.com>  <br/>                                                                                   |

Bei Option 2 basieren einfache URLs auf dem Domänennamen SfB2015.contoso.com. Daher benötigen Sie nur einen DNS-A-Eintrag, der alle drei Arten von einfachen URLs unterstützt. Dieser DNS-A-Eintrag verweist auf SfB2015.contoso.com. Zusätzlich benötigen Sie weiterhin separate DNS-A-Einträge für weitere SIP-Domänen in Ihrer Organisation. 

**Benennung einfacher URLs – Option 2**


| **Einfache URL** <br/> | **Beispiel** <br/>                                                                                                                    |
|:---------------------|:-------------------------------------------------------------------------------------------------------------------------------------|
| Meet  <br/>          | https://SfB2015.contoso.com/Meet, https://SfB2015.fabrikam.com/Meet und so weiter (eine für jede SIP-Domäne in Ihrer Organisation)  <br/> |
| Einwahl  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                                          |
| Admin  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                                           |

Option 3 ist sinnvoll, wenn Sie über zahlreiche SIP-Domänen verfügen und diesen separate einfache URLs für Besprechungen (Meet) zuweisen, jedoch die Anzahl von DNS-Einträgen und die Zertifikatanforderungen für diese einfachen URLs minimieren möchten. 

**Benennung einfacher URLs – Option 3**


| **Einfache URL** <br/> | **Beispiel** <br/>                                                                                                      |
|:---------------------|:-----------------------------------------------------------------------------------------------------------------------|
| Meet  <br/>          | <https://SfB2015.contoso.com/contosoSIPdomain/Meet>  <br/> <https://SfB2015.contoso.com/fabrikamSIPdomain/Meet>  <br/> |
| Einwahl  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                            |
| Admin  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                             |

## <a name="disaster-recovery-option-for-simple-urls"></a>Notfallwiederherstellungsoption für einfache URLs
<a name="BK_Valid"> </a>

Wenn Sie über mehrere Standorte verfügen, die Front-End-Pools enthalten und Ihr DNS-Anbieter GeoDNS unterstützt, können Sie Ihre DNS-Einträge für einfache URLs zur Unterstützung der Notfallwiederherstellung einrichten, sodass die Funktion für einfache URLs auch dann fortgesetzt wird, wenn ein gesamter Front-End-Pool aus dem System geht. Dieses Notfallwiederherstellungsfeature unterstützt die einfachen URLs "Meet" und "Dial-In".

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

Erstellen Sie dann CNAME-Einträge, die Ihre einfache Meet-URL (z. B. meet.contoso.com) in die beiden GeoDNS-Adressen auflösen.

> [!NOTE]
> Wenn in Ihrem Netzwerk das so genannte Hairpinning eingesetzt wird (der gesamte Datenverkehr der einfachen URL wird über den externen Link geleitet, einschließlich des Datenverkehrs aus der Organisation), können Sie einfach nur die externe GeoDNS-Adresse konfigurieren und Ihre einfache Meet-URL nur in diese externe Adresse auflösen.

Wenn Sie diese Methode verwenden, können Sie jede GeoDNS-Adresse so konfigurieren, dass entweder eine Roundrobin-Methode zur Verteilung der Anforderungen an die beiden Pools verwendet wird oder dass hauptsächlich eine Verbindung mit einem Pool hergestellt wird (z. B. mit dem Pool, der geografisch näher ist) und der andere Pool nur bei einem Konnektivitätsfehler zum Einsatz kommt. 

Sie können dieselbe Konfiguration für die einfache Dialin-URL verwenden. Erstellen Sie dazu zusätzliche Einträge wie im vorherigen Beispiel, und ersetzen Sie diese  `dialin` `meet` in den DNS-Einträgen. Verwenden Sie für die einfache Admin-URL eine der weiter oben in diesem Abschnitt aufgelisteten drei Optionen.

Sobald diese Konfiguration eingerichtet ist, müssen Sie eine Überwachungsanwendung verwenden, um die HTTP-Überwachung so einzurichten, dass nach Fehlern Ausschau gehalten wird. Überwachen Sie den externen Zugriff, um sicherzustellen, dass HTTPS GET lyncdiscover verwendet wird.<sipdomain> Anforderungen an den externen Web-FQDN oder die Load Balancer-IP-Adresse für die beiden Pools sind erfolgreich. Beispielsweise dürfen die folgenden Anforderungen keinen **ACCEPT**-Header enthalten und müssen **200 OK** zurückgegeben.

```console
HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

For internal access, you must monitor port 5061 on the internal web FQDN or load balancer IP address for the two pools. Wenn Konnektivitätsfehler erkannt werden, muss die VIP für diese Pools die Ports 80, 443 und 4443 schließen.


