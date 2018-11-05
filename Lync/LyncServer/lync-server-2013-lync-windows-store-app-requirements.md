---
title: Anforderungen für Lync Windows Store-App
TOCTitle: Anforderungen für Lync Windows Store-App
ms:assetid: 5f2e0a40-8450-4f61-b6f6-913fc1906020
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ823129(v=OCS.15)
ms:contentKeyID: 52056347
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anforderungen für Lync Windows Store-App

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Organisationen mit einer lokalen Bereitstellung von Lync Server müssen die folgenden Voraussetzungen erfüllen, damit Windows Store-App für Lync unterstützt wird.


> [!NOTE]
> Führen Sie für Lync Server 2010 auf allen Servern das kumulative Update für Lync Server 2010 vom Februar 2012 oder höher aus (verfügbar unter <A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352">http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2670352</A>). Soll es Benutzern möglich sein, an Besprechungen teilzunehmen, führen Sie auf den Servern das kumulative Update für Lync Server 2010 vom Oktober 2012 aus (verfügbar unter <A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915">http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2737915</A>).



  - Aktivieren Sie auf dem Server die Dienste AutoErmittlung, Lync Web App und Webticket.

  - Aktivieren Sie Zertifikatauthentifizierung auf dem Front-End-Server oder im Front-End-Pool. (Der Benutzerregistrierungsprozess auf dem Front-End-Server oder im Front-End-Pool wird häufig als die Registrierungsstelle bezeichnet.) Ausführlichere Informationen hierzu finden Sie unter [Erstellen von Registrierungskonfigurationseinstellungen](lync-server-2013-create-registrar-configuration-settings.md).

  - Veröffentlichen Sie DNS-Aliasressourceneinträge (CNAME) für den AutoErmittlungsdienst.

  - Es ist nicht mehr erforderlich sicherzustellen, dass der Zertifikatssperrlisten-Verteilungspunkt für die für Lync Server ausgestellten Zertifikate auf eine HTTP-Ressource verweist anstatt auf eine LDAP-Ressource. Sie müssen jedoch sicherstellen, dass auf den Clientcomputern die neuesten Windows-Updates installiert sind.

  - Konfigurieren Sie HTTP-Proxys im Unternehmen so, dass diese HTTP-Datenverkehr von Lync Server zulassen. Fügen Sie erforderlichenfalls Ausnahmen für die Dienste AutoErmittlung, Lync Web App und Webticket hinzu.

  - Installieren Sie auf Clients Windows 8.1 und die neueste Version von Windows Store-App für Lync, um ein Anmeldeproblem zu beheben, das im Allgemeinen auftritt, wenn Sie mehrere Domänen verwenden (zum Beispiel wenn der SIP-URI <strong>userA@domainZ.com</strong>, der Edgeserver aber **sip.domainX.com** ist).

Wenn für Ihre Organisation ein Abonnement bei Lync Online oder Office 365 besteht und Sie Ihren eigenen Domänennamen verwenden, müssen Sie weitere Schritte ausführen, um Ihr Netzwerk für die automatische Ermittlung von Lync-Servern einzurichten. Auf mobilen Geräten sind die Netzwerkkonfigurationsanforderungen für Windows Store-App für Lync und Lync identisch. Gehen Sie gemäß den Anweisungen vor, die Sie unter "Set up your network" im Office 365 Wiki-Artikel "Set up Lync mobile devices" finden, der unter [http://go.microsoft.com/fwlink/?LinkId=271822](http://go.microsoft.com/fwlink/?linkid=271822) verfügbar ist.

## Siehe auch

#### Konzepte

[Bereitstellen der Lync-Windows Store-App](lync-server-2013-deploying-lync-windows-store-app.md)

