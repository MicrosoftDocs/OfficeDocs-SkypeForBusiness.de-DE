---
title: Konfigurationsanforderungen für Reverseproxy in Lync Server 2013
TOCTitle: Konfigurationsanforderungen für Reverseproxy in Lync Server 2013
ms:assetid: c37d688a-28e4-4822-80cc-6add59c71052
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ945651(v=OCS.15)
ms:contentKeyID: 52056453
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurationsanforderungen für Reverseproxy in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-03-05_

Lync Server 2013 stellt einige Anforderungen an die Kommunikation über den externen Client, die dann an die auf dem Director, Directorpool, Front-End-Server oder Front-End-Pool gehosteten externen Webdienste übergeben wird. Der Reverseproxy ist auch für die Veröffentlichung der Office Web Apps-Server verantwortlich, wenn Sie Ihren Benutzern Konferenzfunktionen anbieten.


> [!NOTE]
> Lync Server 2013 gibt keinen bestimmten Reverseproxy vor, der verwendet werden muss. Lync Server 2013 definiert nur betriebliche Anforderungen, die der Reverseproxy ausführen muss. Normalerweise kann der Reverseproxy, den Sie bereits in der Infrastruktur bereitgestellt haben, die Anforderungen erfüllen.



## Reverseproxyanforderungen

In Lync Server 2013 wird erwartet, dass ein Reverseproxy folgende funktionalen Vorgänge ausführt:

  - Der Reverseproxy verwendet Secure Socket Layer (SSL) und Transport Layer Security (TLS), die mit Zertifikaten von einer öffentlichen Zertifizierungsstelle implementiert wurden, um eine Verbindung mit den veröffentlichten externen Webdienste herzustellen, die auf dem bzw. im Director, Directorpool, Front-End-Server oder Front-End-Pool gehostet werden. Der Director und der Front-End-Server können mithilfe von Hardwaregeräten zum Lastenausgleich in einem Pool mit Lastenausgleich platziert werden.

  - Kann öffentliche interne Websites mithilfe von Zertifikaten für die Verschlüsselung veröffentlichen oder diese bei Bedarf unverschlüsselt veröffentlichen.

  - Kann eine intern gehostete Website extern mit einem vollqualifizierten Domänenennamen (FQDN) veröffentlichen.

  - Kann den gesamten Inhalt der gehosteten Website veröffentlichen. Standardmäßig können Sie die **/\***-Direktive verwenden, die für die meisten Webserver folgende Bedeutung hat: "Gesamten Inhalt auf dem Webserver veröffentlichen." Sie können die Direktive auch ändern, z. B. in **/Uwca/\***. Das bedeutet: "Sämtlichen Inhalt im virtuellen Verzeichnis "Ucwa" veröffentlichen."

  - Muss konfigurierbar sein, um SSL- und/oder TLS- Verbindungen mit Clients vorauszusetzen, die Inhalt von einer veröffentlichten Website anfordern.

  - Muss Zertifikate mit SAN-Einträgen (alternative Antragstellernamen) akzeptieren.

  - Muss in der Lage sein, die Zertifikatbindung an Listener oder Schnittstellen zu erlauben, über die der FQDN der externen Webdienste aufgelöst wird. Listenerkonfigurationen sind den Schnittstellen vorzuziehen. Viele Listener können in einer einzelnen Schnittstelle konfiguriert werden.

  - Müssen die Konfiguration der Hostheaderbehandlung zulassen. Häufig muss der ursprüngliche Hostheader, der vom anfordernden Client gesendet wurde, transparent übergeben werden, anstatt durch den Reverseproxy geändert zu werden.

  - Überbrücken des SSL- und TLS-Datenverkehrs von genau einem definierten Port (z. B. TCP 443) zu einem anderen definierten Port (z. B. TCP 4443). Der Reverseproxy kann das Paket bei Empfang entschlüsseln und dann beim Senden wieder verschlüsseln.

  - Überbrücken des unverschlüsselten TCP-Datenverkehrs von einem Port (z. B. TCP 80) zu einem anderen Port (z. B. TCP 8080).

  - Zulassen oder Akzeptieren der Konfiguration von NTLM-Authentifizierung, keiner Authentifizierung oder Pass-Through-Authentifizierung.

