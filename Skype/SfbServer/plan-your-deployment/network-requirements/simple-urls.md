---
title: DNS-Anforderungen für einfache URLs in Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
description: 'Zusammenfassung: Überprüfen Sie die einfache URL Aspekte in diesem Thema vor der Implementierung von DNS-Einträgen für Skype für Business Server.'
ms.openlocfilehash: 6e62190f19969e635690a68ead4f2c96a32a27c2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920236"
---
# <a name="dns-requirements-for-simple-urls-in-skype-for-business-server"></a>DNS-Anforderungen für einfache URLs in Skype für Business Server

**Zusammenfassung:** Überprüfen Sie vor der Implementierung von DNS-Einträgen für Skype für Business Server die einfache URL Aspekte in diesem Thema.

Einfache URLs vereinfachen den benutzerbeitritt zu Besprechungen für Ihre Benutzer und erleichtern den Zugriff auf Skype für Business Server-Verwaltungstools Administratoren. Einfache URLs verwenden der eigenen Domäne, die nicht der SIP-Domänen übereinstimmen muss, die Sie definieren. 

Skype für Business Server unterstützt die folgenden drei einfache URLs: Dial-In und Portals erfüllen Sie sind erforderlich, um einfache URLs für die Besprechung und Einwahl einzurichten, und die einfache Admin-URL ist optional. Die Domain Name System (DNS)-Datensätze, die Sie zur Unterstützung von einfachen URLs müssen hängen davon ab, wie Sie diese einfachen URLs definiert haben, und ob Sie Disaster Recovery für einfache URLs unterstützen möchten. 

## <a name="simple-url-scope"></a>Einfache URL-Bereichs

Sie können von einfachen URLs damit globalen Ebene konfigurieren, oder Sie können verschiedener einfacher URLs für jeder zentrale Standort in Ihrer Organisation angeben. Wenn eine globale einfache URL und eine einfache Website-URL angegeben ist, hat die einfache Website-URL Vorrang vor. 

In den meisten Fällen wird empfohlen, Sie nur auf globaler Ebene, einfache URLs festlegen, sodass Meet einfache URL eines Benutzers nicht geändert wird, wenn sie von einer Website in eine andere verschieben. Die Ausnahme wäre Organisationen, die unterschiedliche Telefonnummern für DFÜ-Benutzer an verschiedenen Standorten verwenden müssen. Beachten Sie, dass wenn Sie eine einfache URL (beispielsweise die Zugriffsnummer für Einwahl einfache URL) an einem Standort zu einer einfachen URL auf Standortebene festlegen, müssen Sie einfache URLs an diesem Standort Standort-als auch werden auch festlegen.

Sie können globale einfache URLs im Topologie-Generator festlegen. Um eine einfache URL auf der Websiteebene festzulegen, verwenden Sie das Cmdlet "Set-CsSimpleURLConfiguration".

Definieren eine einfache URL benötigen ebenfalls einen A und/oder AAAA-Eintrag in Ihrer DNS-Konfiguration festlegen.

## <a name="simple-url-naming-and-validation-rules"></a>Einfache URL naming und Validierung Regeln
<a name="BK_Valid"> </a>

Erzwingen der Topologie-Generator und die Skype für Business Server-Verwaltungsshell-Cmdlets mehrerer Gültigkeitsregeln für von einfachen URLs. Sie sind erforderlich, um einfache URLs für erfüllen und "Dialin" festgelegt, aber eine einfache Admin festlegen ist optional. Jede SIP-Domäne muss eine separate einfache Meet-URL haben, aber Sie benötigen nur eine einfache Dialin-URL und eine einfache Admin-URL für die gesamte Organisation.

Jede einfache URL in Ihrer Organisation benötigen einen eindeutigen Namen und ein Präfix aus einer anderen einfache URL ist nicht möglich (beispielsweise Sie konnte nicht SfB2015.contoso.com/Meet als die einfache Meet-URL und SfB2015.contoso.com/Meet/Dialin Dialin einfache URL festgelegt). Einfache URL dürfen nicht den FQDN eines Pools oder Portinformationen enthalten (z. B. https://FQDN:88/meet ist nicht zulässig). Alle einfachen URLs müssen mit dem Präfix https:// beginnen. 

Einfache URLs darf nur alphanumerische Zeichen enthalten (d. h., a – Z, A – Z, 0-9 und dem Punkt (.). Wenn Sie andere Zeichen verwenden, die einfache URLs funktioniert möglicherweise nicht wie erwartet.

## <a name="changing-simple-urls-after-deployment"></a>Ändern von einfachen URLs nach der Bereitstellung
<a name="BK_Valid"> </a>

Wenn Sie nach der anfänglichen Bereitstellung eine einfache URL ändern, müssen Sie berücksichtigen wie die Änderung Ihrer DNS-Einträgen und Zertifikaten für einfache URLs auswirkt. Wenn die Basis einer einfachen URL ändert, müssen Sie die DNS-Einträgen und Zertifikaten sowie ändern. Beispiel: Ändern von https://SfB2015.contoso.com/Meet auf https://meet.contoso.com die base-URL von SfB2015.contoso.com in meet.contoso.com, geändert, damit Sie die DNS-Einträgen und Zertifikaten verweisen auf meet.contoso.com ändern müssen. Wenn Sie die einfache URL aus geändert https://SfB2015.contoso.com/Meet auf https://SfB2015.contoso.com/Meetings, die Basis-URL SfB2015.contoso.com bleibt, also keine DNS oder zertifikatänderungen erforderlich sind.

Wenn Sie einen einfachen URL-Name ändern, müssen Sie **Enable-CsComputer** auf jedem Director und Front-End-Server, um die Änderung zu registrieren ausführen.

## <a name="naming-examples-for-simple-urls"></a>Benennen Beispiele für einfache URLs
<a name="BK_Valid"> </a>

Es gibt drei Empfohlene Optionen für das Benennen von einfachen URLs. Welche Option Sie wählen wirkt sich wie Sie Ihre DNS-A-Einträgen und Zertifikaten die Unterstützung für einfache URLs eingerichtet. In jeder Option müssen Sie eine einfache Meet-URL für jede SIP-Domäne in Ihrer Organisation konfigurieren. 

Sie benötigen immer nur eine einfache URL in der gesamten Organisation für Einwahl und eine einfache Admin, unabhängig davon, wie viele SIP-Domänen, die Sie verwenden.

Bei Option 1 erstellen Sie einen neuen SIP-Domänennamen für jede einfache URL.

Wenn Sie diese Option verwenden, benötigen Sie einen separaten DNS-A-Eintrag für jede einfache URL, und jeder einfache Meet-URL in Ihren Zertifikaten benannt sein muss.

**Benennung einfacher URLs – Option 1**


| **Einfache URL** <br/> | **Beispiel** <br/>                                                                                                    |
|:---------------------|:---------------------------------------------------------------------------------------------------------------------|
| Erfüllen  <br/>          | https://meet.contoso.com, https://meet.fabrikam.comund so weiter (eine für jede SIP-Domäne in Ihrer Organisation)  <br/> |
| Einwahl  <br/>       | <https://dialin.contoso.com>  <br/>                                                                                  |
| Admin  <br/>         | <https://admin.contoso.com>  <br/>                                                                                   |

Mit der Option 2 sind einfache URLs auf dem Domänennamen SfB2015.contoso.com basiert. Aus diesem Grund benötigen Sie nur ein DNS-A-Eintrag alle drei Arten von einfachen URLs ermöglicht. Dieser DNS-A-Eintrag verweist auf SfB2015.contoso.com. Darüber hinaus benötigen Sie weiterhin separate DNS-A-Einträge für andere SIP-Domänen in Ihrer Organisation. 

**Benennung einfacher URLs – Option 2**


| **Einfache URL** <br/> | **Beispiel** <br/>                                                                                                                    |
|:---------------------|:-------------------------------------------------------------------------------------------------------------------------------------|
| Erfüllen  <br/>          | https://SfB2015.contoso.com/Meet, https://SfB2015.fabrikam.com/Meetund so weiter (eine für jede SIP-Domäne in Ihrer Organisation)  <br/> |
| Einwahl  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                                          |
| Admin  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                                           |

Option 3 ist besonders nützlich, wenn Sie viele SIP-Domänen verfügen, und Sie sollen separate Meet einfache URLs haben jedoch die Anforderungen der DNS-Datensatz und Zertifikat für diese einfache URLs minimieren möchten. 

**Benennung einfacher URLs – Option 3**


| **Einfache URL** <br/> | **Beispiel** <br/>                                                                                                      |
|:---------------------|:-----------------------------------------------------------------------------------------------------------------------|
| Erfüllen  <br/>          | <https://SfB2015.contoso.com/contosoSIPdomain/Meet>  <br/> <https://SfB2015.contoso.com/fabrikamSIPdomain/Meet>  <br/> |
| Einwahl  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                            |
| Admin  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                             |

## <a name="disaster-recovery-option-for-simple-urls"></a>Notfallwiederherstellungsoption für einfache URLs
<a name="BK_Valid"> </a>

Wenn Sie verfügen über mehrere Standorte, die Front-End-Pools enthalten und Ihrem DNS-Anbieter GeoDNS unterstützt, können Sie Ihre DNS-Einträge für einfache URLs zur Unterstützung von Disaster Recovery und einrichten, sodass einfache URL-Funktionalität wird fortgesetzt, auch wenn eine gesamte Front-End-Pool ausfällt. Dieses Disaster Recovery-Feature unterstützt die erfüllen und Einwahl einfache URLs.

Um dies zu konfigurieren, erstellen Sie zwei GeoDNS-Adressen. Jede Adresse verfügt über zwei DNS-A- oder CNAME-Datensätze, die in beiden Pools aufgelöst, die für Disaster Recovery miteinander kombiniert werden. Eine GeoDNS-Adresse für den internen Zugriff verwendet wird, und der interne Web-FQDN oder die Last zum Lastenausgleich IP-Adresse für die beiden Pools aufgelöst wird. GeoDNS Adresse für den externen Zugriff verwendet wird und der externe Webdienste FQDN oder die Load Balancer IP-Adresse für die beiden Pools aufgelöst wird. Es folgt ein Beispiel für die einfache Meet-URL, verwenden die FQDNs für die Pools. 

```
Meet-int.geolb.contoso.com
     Pool1InternalWebFQDN.contoso.com
     Pool2InternalWebFQDN.contoso.com
```

```
Meet-ext.geolb.contoso.com
     Pool1ExternalWebFQDN.contoso.com
     Pool2ExternalWebFQDN.contoso.com
```

Erstellen Sie dann CNAME-Einträge, die die einfache Meet-URL (beispielsweise meet.contoso.com) in die beiden GeoDNS-Adressen aufgelöst.

> [!NOTE]
> Wenn Ihr Netzwerk verwendet Hairpinning (routing alle einfache URL-Datenverkehr über die externe Verknüpfung, einschließlich Datenverkehr, der in Ihrem Unternehmen stammen), klicken Sie dann Sie einfach konfigurieren Sie die externe GeoDNS-Adresse und die einfache Meet-URL nur dem Auflösen externe Adresse.

Wenn Sie diese Methode verwenden, können Sie jede GeoDNS-Adresse zur Verwendung konfigurieren eine Roundrobin-Methode zum Verteilen von Anforderungen an die beiden Pools oder zum Verbinden in erster Linie mit einem Pool (wie der Pool befindet sich geografisch näher), und verwenden Sie das andere Pool nur im Fall von Konnektivitätsfehler. 

Sie können die gleiche Konfiguration für die Einwahl einfache URL einrichten. Erstellen Sie hierzu zusätzliche Datensätze wie im vorherigen Beispiel ersetzen `dialin` für `meet` in den DNS-Einträgen. Verwenden Sie eine der drei weiter oben in diesem Abschnitt aufgeführten Optionen an, für die einfache Admin-URL.

Nachdem Sie diese Konfiguration eingerichtet haben, müssen Sie eine Überwachung Anwendung zum Einrichten von HTTP-Überwachung, für Fehlern Video verwenden. Überwachen Sie für den externen Zugriff, um sicherzustellen, dass diese Lyncdiscover HTTPS erhalten möchten.<sipdomain> Anforderungen an den externen Web-FQDN oder Load Balancer IP-Adresse für die beiden Pools sind erfolgreich. Beispielsweise die folgenden Anforderungen müssen keine **ACCEPT** -Header enthalten und muss zurückgeben **200 OK**.

```
HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

Für den internen Zugriff müssen Sie überwachen Port 5061 am internen FQDN oder IP-Adresse zum Lastenausgleich für die beiden Pools laden. Wenn Verbindungsfehler erkannt werden, muss die VIP-Adresse für diese Pools Ports 80, 443 und 4443 schließen.


