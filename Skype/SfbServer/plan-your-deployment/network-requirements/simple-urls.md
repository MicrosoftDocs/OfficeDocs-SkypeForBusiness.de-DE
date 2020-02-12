---
title: DNS-Anforderungen für einfache URLs in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
description: 'Zusammenfassung: Überprüfen Sie die einfachen URL-Überlegungen in diesem Thema, bevor Sie DNS-Einträge für Skype for Business Server implementieren.'
ms.openlocfilehash: 3296e3678d1d38f021b792a2362f61de66796d0f
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888474"
---
# <a name="dns-requirements-for-simple-urls-in-skype-for-business-server"></a>DNS-Anforderungen für einfache URLs in Skype for Business Server

**Zusammenfassung:** Überprüfen Sie die einfachen URL-Überlegungen in diesem Thema, bevor Sie DNS-Einträge für Skype for Business Server implementieren.

Durch einfache URLs können Sie Ihren Benutzern die Teilnahme an Besprechungen erleichtern und die Verwaltung von Skype for Business Server-Verwaltungstools für Administratoren vereinfachen. Einfache URLs verwenden eine eigene Domäne, die nicht mit den von Ihnen definierten SIP-Domänen übereinstimmen darf. 

Skype for Business Server unterstützt die folgenden drei einfachen URLs: Besprechung, Einwahl und Administrator. Sie müssen einfache URLs für Meet und Dial-in einrichten, und die einfache Administrator-URL ist optional. Die DNS-Einträge (Domain Name System), die Sie zur Unterstützung einfacher URLs benötigen, hängen davon ab, wie Sie diese einfachen URLs definiert haben und ob Sie die Disaster Recovery für einfache URLs unterstützen möchten. 

## <a name="simple-url-scope"></a>Einfacher URL-Bereich

Sie können Ihre einfachen URLs so konfigurieren, dass Sie einen globalen Bereich aufweisen, oder Sie können für jede zentrale Website in Ihrer Organisation unterschiedliche einfache URLs angeben. Wenn sowohl eine globale einfache URL als auch eine einfache URL für eine Website angegeben wird, hat die Website einfache URL Vorrang. 

In den meisten Fällen empfiehlt es sich, einfache URLs nur auf globaler Ebene festzulegen, damit die einfache URL des Benutzers nicht geändert wird, wenn Sie von einer Website zu einer anderen wechseln. Ausnahmen sind Organisationen, die unterschiedliche Telefonnummern für Einwahlbenutzer an verschiedenen Standorten verwenden müssen. Beachten Sie Folgendes: Wenn Sie eine einfache URL (beispielsweise die Einwahl einfache URL) auf einer Website als einfache URL auf Websiteebene festzulegen, müssen Sie auch die anderen einfachen URLs auf dieser Website auf Websiteebene festzulegen.

Sie können globale einfache URLs im Topologie-Generator einrichten. Verwenden Sie das Cmdlet "CsSimpleURLConfiguration", um eine einfache URL auf Websiteebene einzurichten.

Zum Definieren einer einfachen URL muss auch ein a-und/oder AAAA-Eintrag in Ihrer DNS-Konfiguration festgelegt werden.

## <a name="simple-url-naming-and-validation-rules"></a>Einfache URL-Benennungs-und Gültigkeitsprüfungsregeln
<a name="BK_Valid"> </a>

Der Topologie-Generator und die Cmdlets der Skype for Business Server-Verwaltungsshell erzwingen verschiedene Gültigkeitsprüfungsregeln für ihre einfachen URLs. Sie müssen einfache URLs für Meet und Dialin festlegen, die Einstellung für "Administrator" ist jedoch optional. Jede SIP-Domäne muss über eine separate einfache URL-Adresse verfügen, Sie benötigen jedoch nur eine einfache Wähl-URL und eine einfache Administrator-URL für Ihre gesamte Organisation.

Jede einfache URL in Ihrer Organisation muss einen eindeutigen Namen haben und darf kein Präfix einer anderen einfachen URL sein (beispielsweise können Sie SfB2015.contoso.com/Meet nicht als ihre einfache URL und SfB2015.contoso.com/Meet/Dialin als Ihre Einwahl einfache URL festlegen). Einfache URL-Namen dürfen den FQDN eines Pools oder keine Portinformationen (beispielsweise https://FQDN:88/meet nicht zulässig) enthalten. Alle einfachen URLs müssen mit dem https://-Präfix beginnen. 

Einfache URLs können nur alphanumerische Zeichen enthalten (also a-z, a-z, 0-9 und der Punkt (.). Wenn Sie andere Zeichen verwenden, funktionieren die einfachen URLs möglicherweise nicht erwartungsgemäß.

## <a name="changing-simple-urls-after-deployment"></a>Ändern einfacher URLs nach der Bereitstellung
<a name="BK_Valid"> </a>

Wenn Sie nach der anfänglichen Bereitstellung eine einfache URL ändern, müssen Sie wissen, wie sich die Änderung auf Ihre DNS-Einträge und Zertifikate für einfache URLs auswirkt. Wenn sich die Basis einer einfachen URL ändert, müssen Sie auch die DNS-Einträge und Zertifikate ändern. Wenn Sie beispielsweise https://SfB2015.contoso.com/Meet https://meet.contoso.com die Basis-URL von SfB2015.contoso.com in Meet.contoso.com ändern, müssen Sie die DNS-Einträge und Zertifikate so ändern, dass Sie auf Meet.contoso.com verweisen. Wenn Sie die einfache URL von https://SfB2015.contoso.com/Meet in https://SfB2015.contoso.com/Meetingsgeändert haben, bleibt die Basis-URL von SfB2015.contoso.com unverändert, sodass keine DNS-oder Zertifikat Änderungen erforderlich sind.

Wenn Sie jedoch einen einfachen URL-Namen ändern, müssen Sie **enable-CsComputer** auf jedem Director und Front-End-Server ausführen, um die Änderung zu registrieren.

## <a name="naming-examples-for-simple-urls"></a>Beispiele für die Namensgebung für einfache URLs
<a name="BK_Valid"> </a>

Es gibt drei Empfohlene Optionen für das Benennen von einfachen URLs. Welche Option Sie auswählen, hat Auswirkungen auf die Art und Weise, wie Sie Ihre DNS A-Einträge und Zertifikate einrichten, die einfache URLs unterstützen. Bei jeder Option müssen Sie eine einfache URL für jede SIP-Domäne in Ihrer Organisation konfigurieren. 

Sie benötigen immer nur eine einfache URL in ihrer gesamten Organisation für die Einwahl und eine für Administratoren, unabhängig davon, wie viele SIP-Domänen Sie besitzen.

In Option 1 erstellen Sie für jede einfache URL einen neuen SIP-Domänennamen.

Wenn Sie diese Option verwenden, benötigen Sie einen separaten DNS-a-Eintrag für jede einfache URL, und jede einfache URL muss in ihren Zertifikaten benannt sein.

**Einfache URL-Benennungs Option 1**


| **Einfache URL** <br/> | **Beispiel** <br/>                                                                                                    |
|:---------------------|:---------------------------------------------------------------------------------------------------------------------|
| Treffen  <br/>          | https://meet.contoso.comhttps://meet.fabrikam.comusw. (eine für jede SIP-Domäne in Ihrer Organisation)  <br/> |
| Einwahl  <br/>       | <https://dialin.contoso.com>  <br/>                                                                                  |
| Admin  <br/>         | <https://admin.contoso.com>  <br/>                                                                                   |

Bei Option 2 basieren einfache URLs auf dem Domänennamen SfB2015.contoso.com. Daher benötigen Sie nur einen DNS-A-Eintrag, der alle drei Arten von einfachen URLs aktiviert. Dieser DNS-A-Eintrag verweist auf SfB2015.contoso.com. Darüber hinaus benötigen Sie für andere SIP-Domänen in Ihrer Organisation weiterhin getrennte DNS-A-Einträge. 

**Einfache URL-Benennungs Option 2**


| **Einfache URL** <br/> | **Beispiel** <br/>                                                                                                                    |
|:---------------------|:-------------------------------------------------------------------------------------------------------------------------------------|
| Treffen  <br/>          | https://SfB2015.contoso.com/Meethttps://SfB2015.fabrikam.com/Meetusw. (eine für jede SIP-Domäne in Ihrer Organisation)  <br/> |
| Einwahl  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                                          |
| Admin  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                                           |

Option 3 ist am nützlichsten, wenn Sie über viele SIP-Domänen verfügen und diese getrennte einfache URLs erfüllen sollen, aber den DNS-Eintrag und die Zertifikatanforderungen für diese einfachen URLs minimieren möchten. 

**Einfache URL-Benennungs Option 3**


| **Einfache URL** <br/> | **Beispiel** <br/>                                                                                                      |
|:---------------------|:-----------------------------------------------------------------------------------------------------------------------|
| Treffen  <br/>          | <https://SfB2015.contoso.com/contosoSIPdomain/Meet>  <br/> <https://SfB2015.contoso.com/fabrikamSIPdomain/Meet>  <br/> |
| Einwahl  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                            |
| Admin  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                             |

## <a name="disaster-recovery-option-for-simple-urls"></a>Disaster Recovery-Option für einfache URLs
<a name="BK_Valid"> </a>

Wenn Sie über mehrere Websites verfügen, die Front-End-Pools enthalten und Ihr DNS-Anbieter GeoDNS unterstützt, können Sie Ihre DNS-Einträge für einfache URLs einrichten, um die Disaster Recovery zu unterstützen, damit die einfache URL-Funktionalität auch dann fortgesetzt wird, wenn ein ganzer Front-End-Pool ausfällt. Dieses Disaster Recovery-Feature unterstützt die einfachen URLs Meet und Dial-in.

Um dies zu konfigurieren, erstellen Sie zwei GeoDNS-Adressen. Jede Adresse hat zwei DNS-A-oder CNAME-Einträge, die in zwei Pools aufgelöst werden, die für Disaster Recovery-Zwecke kombiniert werden. Eine GeoDNS-Adresse wird für den internen Zugriff verwendet und in die IP-Adresse des internen webfqdn oder des Lastenausgleichsmoduls für die beiden Pools aufgelöst. Die andere GeoDNS-Adresse wird für den externen Zugriff verwendet und in die IP-Adresse des externen webfqdn oder des Load Balancer für die beiden Pools aufgelöst. Im folgenden finden Sie ein Beispiel für die einfache URL "erfüllen" mit den FQDNs für die Pools. 

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

Erstellen Sie dann CNAME-Einträge, die ihre einfache URL (beispielsweise Meet.contoso.com) zu den beiden GeoDNS-Adressen auflösen.

> [!NOTE]
> Wenn in Ihrem Netzwerk hairpinning (Routing aller einfachen URL-Datenverkehr über den externen Link, einschließlich Datenverkehr, der aus Ihrer Organisation stammt), verwendet wird, können Sie einfach die externe GeoDNS-Adresse konfigurieren und ihre einfache URL nur dann auflösen, wenn externe Adresse.

Wenn Sie diese Methode verwenden, können Sie jede GeoDNS-Adresse so konfigurieren, dass entweder eine Round Robin-Methode zum Verteilen von Anforderungen an die beiden Pools verwendet wird, oder wenn Sie eine Verbindung in erster Linie mit einem Pool (wie etwa dem geografisch näher gelegenen Pool) herstellen und den anderen Pool nur verwenden, wenn Verbindungsfehler 

Sie können die gleiche Konfiguration für die Einwahl einfache URL einrichten. Erstellen Sie dazu zusätzliche Datensätze wie im vorherigen Beispiel, die `dialin` `meet` in den DNS-Einträgen ersetzt werden. Verwenden Sie für die einfache Administrator-URL eine der drei oben in diesem Abschnitt aufgeführten Optionen.

Sobald diese Konfiguration eingerichtet ist, müssen Sie eine Überwachungsanwendung verwenden, um die HTTP-Überwachung so einzurichten, dass Fehler überwacht werden. Überwachen Sie für externen Zugriff, um sicherzustellen, dass HTTPS lyncdiscover erhält.<sipdomain> Anforderungen an die externe Web-FQDN-oder Load Balancer-IP-Adresse für die beiden Pools sind erfolgreich. Die folgenden Anforderungen dürfen beispielsweise keinen **Accept** -Header enthalten und müssen **200 OK**zurückgeben.

```console
HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

Für den internen Zugriff müssen Sie Port 5061 auf der internal Web FQDN-oder Load Balancer-IP-Adresse für die beiden Pools überwachen. Wenn Verbindungsfehler erkannt werden, müssen die VIP für diese Pools die Ports 80, 443 und 4443 schließen.


