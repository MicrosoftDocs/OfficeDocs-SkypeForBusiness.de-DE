---
title: 'Lync Server 2013: Überprüfen des Zugriffs über den Reverseproxy'
TOCTitle: Überprüfen des Zugriffs über den Reverseproxy
ms:assetid: 3076a786-e022-4d41-91ec-1bf252b2a468
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg429697(v=OCS.15)
ms:contentKeyID: 49293580
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Überprüfen des Zugriffs über den Reverseproxy in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-03-29_

Überprüfen Sie mit dem folgenden Verfahren, ob die Benutzer auf Informationen auf dem Reverseproxy zugreifen können. Möglicherweise müssen Sie die Firewall- und die DNS-Konfiguration (Domain Name System) vollständig abschließen, bevor der Zugriff ordnungsgemäß funktioniert.

## So überprüfen Sie den Zugriff über das Internet auf die Website

  - Öffnen Sie einen Webbrowser, und geben Sie in der Adressleiste die URLs ein, die von den Clients für den Zugriff auf die Adressbuchdateien und die Website für Konferenzen verwendet werden.
    
      - Geben Sie für den Adressbuchserver eine URL ähnlich der folgenden ein: **https:// *Externer FQDN der Webfarm* /abs**, wobei *Externer FQDN der Webfarm* für den externen FQDN der externen Webdienste steht, die Adressbuchdienste hosten. Der Benutzer sollte eine HTTP-Anforderung erhalten, da die Verzeichnissicherheit für den Ordner des Adressbuchservers standardmäßig für die Windows-Authentifizierung konfiguriert ist.
    
      - Geben Sie für Konferenzen eine URL ähnlich der folgenden ein: **https:// *Externer FQDN der Webfarm* /meet**, wobei *Externer FQDN der Webfarm* für den externen FQDN der Webfarm steht, die die Besprechungsinhalte hostet. Unter dieser URL sollte die Problembehandlungsseite für Konferenzen angezeigt werden. Überprüfen Sie alternativ, ob Ihre einfache URL für Konferenzen korrekt funktioniert. Beispiel für eine einfache URL für den Konferenzbeitritt: https://meet.contoso.com.
    
      - Geben Sie für die Verteilergruppenerweiterung eine URL ähnlich der folgenden ein: **https:// *Externer FQDN der Webfarm* /GroupExpansion/service.svc**. Der Benutzer sollte eine HTTP-Anforderung erhalten, weil die Verzeichnissicherheit für den Erweiterungsdienst von Verteilergruppen standardmäßig für die Windows-Authentifizierung konfiguriert ist.
    
      - Geben Sie für Einwahlkonferenzen eine einfache URL ähnlich der folgenden ein: **https:// *Externer FQDN der Webfarm* /dialin**, wobei *Externer FQDN der Webfarm* für den externen FQDN der Webfarm steht, die die Seite zur Einwahl für Einwahlkonferenzen hostet. Der Benutzer sollte auf die Seite zur Einwahl geleitet werden. Überprüfen Sie alternativ, ob Ihre einfache URL für Einwahlkonferenzen korrekt funktioniert. Beispiel für eine einfache URL für Einwahlkonferenzen: https://dialin.contoso.com.
    
      - Wenn Sie bestätigen möchten, dass die AutoErmittlung-URL funktioniert, geben Sie "https://lyncdiscover. *ExterneDomäneFQDN* " ein. Der Browser sollte Sie auffordern, eine Datei zu öffnen. Wählen Sie Editor aus, um die Datei zu öffnen. Eine typische Antwort sieht wie folgt aus:
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

