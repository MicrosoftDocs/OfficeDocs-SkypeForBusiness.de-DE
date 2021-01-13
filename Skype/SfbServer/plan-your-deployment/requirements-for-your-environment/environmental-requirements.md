---
title: Umgebungsanforderungen für Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/15/2018
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
ms.assetid: 4812c444-2546-48d7-9ca7-b71fce508ed8
description: 'Zusammenfassung: Konfigurieren Sie Ihre Nicht-Server-Anforderungen für Skype for Business Server 2015. Es gibt eine Vielzahl von Dinge, die Sie vor der Bereitstellung konfigurieren möchten, z. B. Active Directory, DNS, Certs und Fileshares.'
ms.openlocfilehash: 83e01cec8bea5a45debadcf8ef9167ddd53b6a46
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832135"
---
# <a name="environmental-requirements-for-skype-for-business-server-2015"></a>Umgebungsanforderungen für Skype for Business Server 2015
 
**Zusammenfassung:** Konfigurieren Sie Ihre Nicht-Server-Anforderungen für Skype for Business Server 2015. Es gibt eine Vielzahl von Dinge, die Sie vor der Bereitstellung konfigurieren möchten, z. B. Active Directory, DNS, Certs und Fileshares.
  
Was ist eine Umgebungsanforderung für Skype for Business Server 2015? Nun, wir haben alles, was sich nicht direkt auf den Server bezogen hat, in dieses Thema bezogene daten, sodass Sie nicht so viel herumklicken müssen. Wenn Sie nach servervoraussetzungen komponenten suchen, können Sie sich die Serveranforderungen für Skype [](../../plan-your-deployment/network-requirements/network-requirements.md) [for Business Server 2015](server-requirements.md) Dokument. Netzwerkplanung ist auch separat dokumentiert. Andernfalls ist dies das, was wir in diesem Artikel haben:
  
- [Active Directory](environmental-requirements.md#AD)
  
- [Domain Name System (DNS)](environmental-requirements.md#DNS)
  
- [Zertifikate](environmental-requirements.md#Certs)
  
- [Dateifreigabe](environmental-requirements.md#Fileshare)
  
## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

Während viele Konfigurationsdaten für Server und Dienste im zentralen Verwaltungsspeicher von Skype for Business Server 2015 gespeichert sind, sind einige Dinge noch in Active Directory gespeichert:
  
|**Active Directory-Objekte**|**Objekttypen**|
|:-----|:-----|
|Schemaerweiterungen  <br/> |Benutzerobjekterweiterungen  <br/> |
||Erweiterungen für Lync Server 2013 und Lync Server 2010 zur Aufrechterhaltung der Abwärtskompatibilität mit den vorherigen unterstützten Versionen.  <br/> |
|Daten  <br/> |Benutzer-SIP-URI und andere Benutzereinstellungen  <br/> |
||Kontaktobjekte für Anwendungen (z. B. die Reaktionsgruppe und die Konferenz attendant-Anwendung).  <br/> |
||Daten, die aus Abwärtskompatibilität veröffentlicht wurden.  <br/> |
||Ein Dienststeuerungspunkt (Service Control Point, SCP) für den zentralen Verwaltungsspeicher.  <br/> |
||Das Kerberos-Authentifizierungskonto (ein optionales Computerobjekt).  <br/> |
   
### <a name="os-for-domain-controllers"></a>Betriebssystem für Domänencontroller

Welches Domänencontrollerbetriebssystem kann also verwendet werden? Wir haben die folgende Liste:

- Windows Server 2019 (Sie müssen über das kumulative Update 5 oder höher für Skype for Business Server 2015 verfügen)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
Jetzt müssen die Domänenfunktionsebene jeder Domäne, in der Sie Skype for Business Server 2015 bereitstellen, und die Gesamtstrukturfunktionsebene jeder Gesamtstruktur, in der Sie Skype for Business Server 2015 bereitstellen, eine der folgenden Sein:

- Windows Server 2019 (Sie müssen über das kumulative Update 5 oder höher für Skype for Business Server 2015 verfügen)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
- Windows Server 2003
    
Können in diesen Umgebungen schreibgeschützte Domänencontroller vorhanden sein? Sicher, solange auch beschreibbare Domänencontroller am gleichen Standort wie Skype for Business Server verfügbar sind.
  
Jetzt ist es wichtig zu wissen, dass Skype for Business Server 2015 keine Domänen mit einzelner Bezeichnung unterstützt. Was sind sie? Wenn Sie über eine Stammdomäne mit der Bezeichnung "contoso.local" verfügen, ist dies in Ordnung. Wenn Sie über eine Stammdomäne verfügen, die nur als "lokal" bezeichnet wird, funktioniert dies nicht und wird daher nicht unterstützt. Etwas mehr darüber wurde [in diesem Knowledge Base-Artikel geschrieben.](https://support.microsoft.com/kb/300684/en-us)
  
Skype for Business Server 2015 unterstützt auch das Umbenennen von Domänen nicht. Wenn Sie dies wirklich tun müssen, müssen Sie Skype for Business Server 2015 deinstallieren, die Domäne umbenennen und Dann Skype for Business Server 2015 neu installieren.
  
Schließlich können Sie es mit einer Domäne mit einer gesperrten AD DS-Umgebung zu tun haben, und das ist alles in Ordnung. Weitere Informationen zur Bereitstellung von Skype for Business Server 2015 in dieser Art von Umgebung finden Sie in den Bereitstellungs-Dokumenten.
  
### <a name="ad-topologies"></a>AD-Topologien

Die von Skype for Business Server 2015 unterstützten Topologien sind:
  
- Einzelne Gesamtstruktur mit einzelner Domäne
    
- Einzelne Gesamtstruktur mit einer Struktur und mehreren Domänen
    
- Einzelne Gesamtstruktur mit mehreren Strukturen und nicht zusammenhängenden Namespaces
    
- Mehrere Gesamtstrukturen in einer Topologie mit zentraler Gesamtstruktur
    
- Mehrere Gesamtstrukturen in einer Topologie mit Ressourcengesamtstruktur
    
- Mehrere Gesamtstrukturen in einer Skype for Business-Ressourcen-Gesamtstruktur-Topologie mit Exchange Online
    
- Mehrere Gesamtstrukturen in einer Ressourcenstrukturtopologie mit Skype for Business Online und Azure Active Directory Connect
    
Wir verfügen über Diagramme und Beschreibungen, mit deren Hilfe Sie bestimmen können, welche Topologie In Ihrer Umgebung vorhanden ist oder was Sie vor der Installation von Skype for Business Server 2015 einrichten müssen. Um es einfach zu halten, bieten wir auch einen Schlüssel an:
  
![Dies ist ein Schlüssel zu den Symbolen, die für Skype for Business-Topologiediagramme verwendet werden.](../../media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>Einzelne Gesamtstruktur mit einzelner Domäne

![Diagramm einer einzelnen Active Directory-Gesamtstruktur mit einer einzelnen Domäne](../../media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
Dies wird nicht einfacher, es handelt sich um eine Gesamtstruktur mit einer einzigen Domäne, dies ist eine gemeinsame Topologie.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>Einzelne Gesamtstruktur mit einer Struktur und mehreren Domänen

![Diagramm einer einzelnen Gesamtstruktur, einzelner Struktur und Mutipledomänen](../../media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
Dieses Diagramm zeigt wiederum eine einzelne Gesamtstruktur, hat aber auch eine oder mehrere untergeordnete Domänen (in diesem beispiel sind drei enthalten). Die Domäne, in der die Benutzer erstellt werden, kann sich also von der Domäne unterscheiden, in der Skype for Business Server 2015 bereitgestellt wird. Warum sollten Sie sich Gedanken darüber machen? Bei der Bereitstellung eines Skype for Business Server-Front-End-Pools müssen sich alle Server in diesem Pool in einer einzigen Domäne befinden. Sie können die domänenübergreifende Verwaltung über die Unterstützung von universellen Windows-Administratorgruppen in Skype for Business Server nutzen.
  
Zurück zum obigen Diagramm können Sie sehen, dass Benutzer aus einer Domäne auf Skype for Business Server-Pools aus derselben Domäne oder aus unterschiedlichen Domänen zugreifen können, auch wenn sich diese Benutzer in einer untergeordneten Domäne befinden.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>Einzelne Gesamtstruktur mit mehreren Strukturen und nicht zusammenhängenden Namespaces

![Diagramm mit einer einzelnen Gesamtstruktur, mehreren Baumstrukturen und nicht einheitlichen Namespaces](../../media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
Es kann sein, dass Sie über eine Topologie wie dieses Diagramm verfügen, in der Sie eine Gesamtstruktur haben, aber innerhalb dieser Gesamtstruktur mehrere Domänen mit separaten AD-Namespaces. Wenn dies der Fall ist, ist dieses Diagramm eine gute Illustration, da wir Benutzer in drei verschiedenen Domänen haben, die auf Skype for Business Server 2015 zugreifen. Einfarbige Linien deuten darauf hin, dass sie in ihrer eigenen Domäne auf einen Skype for Business Server-Pool zugreifen, während eine gestrichelte Linie angibt, dass sie zu einem Pool in einer anderen Struktur gehen.
  
Wie Sie sehen können, können Benutzer in derselben Domäne, derselben Struktur oder sogar einer anderen Struktur erfolgreich auf Pools zugreifen.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>Mehrere Gesamtstrukturen in einer Topologie mit zentraler Gesamtstruktur

![Diagramm mit mehreren Gesamtstrukturen in einer Topologie mit zentraler Gesamtstruktur](../../media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype for Business Server 2015 unterstützt mehrere Gesamtstrukturen, die in einer Topologie mit zentraler Gesamtstruktur konfiguriert sind. Wenn Sie nicht sicher sind, was Sie haben, verwendet die zentrale Gesamtstruktur in der Topologie Objekte in der Topologie, um Benutzer in den anderen Gesamtstrukturen zu repräsentieren, und hostet Benutzerkonten für alle Benutzer in der Gesamtstruktur.
  
Wie funktioniert dies? Nun, ein Produkt für die Verzeichnissynchronisierung (z. B. Forefront Identity Manager oder FIM) verwaltet die Benutzerkonten Ihrer Organisation während ihres Bestehens. Wenn ein Konto erstellt oder aus einer Gesamtstruktur gelöscht wird, wird diese Änderung mit dem entsprechenden Kontakt in der zentralen Gesamtstruktur synchronisiert.
  
Wenn Ihre AD-Infrastruktur vorhanden ist, ist der Umstieg auf diese Topologie möglicherweise nicht einfach, aber wenn Sie bereits vorhanden sind oder ihre Gesamtstrukturinfrastruktur noch planen, kann dies eine gute Wahl sein. Sie können Ihre Skype for Business Server 2015-Bereitstellung in einer einzelnen Gesamtstruktur zentralisieren, während Benutzer die Anwesenheit anderer Benutzer in einer beliebigen Gesamtstruktur suchen, kommunizieren und anzeigen können. Alle Updates für Benutzerkontakte werden automatisch mit Synchronisierungssoftware behandelt.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Mehrere Gesamtstrukturen in einer Skype for Business-Ressourcen-Gesamtstruktur-Topologie
<a name="BKMK_multipleforestopology"> </a>

![Diagramm mit mehreren Gesamtstrukturen in einer Topologie der Ressourcen gesamtstruktur](../../media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
Eine #A0 wird ebenfalls unterstützt. Hier wird eine Gesamtstruktur für die Ausführung Ihrer Serveranwendungen wie Microsoft Exchange Server und Skype for Business Server 2015 verwendet. Diese Ressourcenforstungen hosten auch eine synchronisierte Darstellung aktiver Benutzerobjekte, aber keine anmeldefähigen Benutzerkonten. Die Ressourcen forest ist also eine Umgebung für gemeinsame Dienste für andere Gesamtstrukturen, in denen sich Benutzerobjekte befinden, und sie haben eine Vertrauensstellung auf Gesamtstrukturebene mit der Ressourcen-Gesamtstruktur.
  
Beachten Sie Exchange Server in derselben Ressourcen gesamtstruktur wie Skype for Business Server oder in einer anderen Gesamtstruktur bereitgestellt werden kann.
  
Zum Bereitstellen von Skype for Business Server 2015 in dieser Topologie würden Sie ein deaktiviertes Benutzerobjekt in der Ressourcen gesamtstruktur für jedes Benutzerkonto in den Benutzer gesamtstrukturen erstellen (wenn Microsoft Exchange Server bereits in der Umgebung vorhanden ist, kann dies für Sie erledigt werden). Anschließend benötigen Sie ein Verzeichnissynchronisierungstool (z. B. Forefront Identity Manager oder FIM), um Benutzerkonten über ihren Lebenszyklus zu verwalten.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Mehrere Gesamtstrukturen in einer Skype for Business-Ressourcen-Gesamtstruktur-Topologie mit Exchange Online
<a name="BKMK_multipleforestopology"> </a>

Diese Topologie ähnelt der Topologie, die in mehreren [Gesamtstrukturen in einer Skype for Business-Ressourcen-Gesamtstruktur-Topologie beschrieben wird.](environmental-requirements.md#BKMK_multipleforestopology)
  
In dieser Topologie gibt es eine oder mehrere Benutzer gesamtstrukturen, und Skype for Business Server wird in einer dedizierten Ressourcen gesamtstruktur bereitgestellt. Exchange Server können lokal in derselben Ressourcen gesamtstruktur oder in einer anderen Gesamtstruktur bereitgestellt und für eine Hybridbereitstellung mit Exchange Online konfiguriert werden, oder E-Mail-Dienste können ausschließlich von Exchange Online für die lokalen Konten bereitgestellt werden. Für diese Topologie ist kein Diagramm verfügbar.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Mehrere Gesamtstrukturen in einer Ressourcenstrukturtopologie mit Skype for Business Online und Azure Active Directory Connect
<a name="BKMK_multipleforestopology"> </a>

![Zeigt zwei AD-Gesamtstrukturen, eine Benutzer- und eine Ressourcen gesamtstruktur an. Die beiden Gesamtstrukturen haben eine Vertrauensstellung. Sie werden mit Microsoft 365 oder Office 365 mithilfe von Azure AD Connect synchronisiert. Alle Benutzer sind über Microsoft 365 oder Office 365 für Skype for Business aktiviert.](../../media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
Bei diesem Szenario gibt es mehrere lokale Gesamtstrukturen mit einer Ressourcen-Gesamtstruktur-Topologie. Es besteht eine vollständige Vertrauensstellung zwischen den Active Directory-Gesamtstrukturen. Das Azure Active Directory Connect-Tool wird zum Synchronisieren von Konten zwischen den lokalen Benutzer gesamtstrukturen und Microsoft 365 oder Office 365 verwendet.
  
 Die Organisation verfügt auch über Microsoft 365 oder Office 365 und verwendet [Azure Active Directory Connect,](https://go.microsoft.com/fwlink/p/?LinkId=614836) um ihre lokalen Konten mit Microsoft 365 oder Office 365 zu synchronisieren. Benutzer, die für Skype for Business aktiviert sind, werden über Microsoft 365 oder Office 365 und Skype for Business Online aktiviert. Skype for Business Server wird nicht lokal bereitgestellt.
  
Die Authentifizierung durch einmaliges Anmelden wird von einer Active Directory-Verbunddienste-Farm bereitgestellt, die sich in der Benutzerstruktur befindet.
  
In diesem Szenario wird es unterstützt, Exchange lokal, Exchange Online, eine hybride Exchange-Lösung oder exchange überhaupt nicht bereitgestellt zu haben. (Das Diagramm zeigt nur exchange lokal, aber die anderen Exchange-Lösungen werden ebenfalls vollständig unterstützt.)
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>Mehrere Gesamtstrukturen in einer Ressourcen-Gesamtstruktur-Topologie mit hybriden Skype for Business
<a name="BKMK_multipleforestopology"> </a>

In diesem Szenario gibt es eine oder mehrere lokale Benutzerforstungen, und Skype for Business wird in einer dedizierten Ressourcen gesamtstruktur bereitgestellt und für den Hybridmodus mit Skype for Business Online konfiguriert. Exchange Server können lokal in derselben Ressourcen gesamtstruktur oder in einer anderen Gesamtstruktur bereitgestellt und für eine Hybridbereitstellung mit Exchange Online konfiguriert werden. Alternativ können E-Mail-Dienste ausschließlich von Exchange Online für die lokalen Konten bereitgestellt werden.
  
Weitere Informationen finden Sie unter ["Konfigurieren einer Umgebung mit mehreren Gesamtstrukturen für Skype for Business-Hybridbereitstellungen".](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md)
  
## <a name="domain-name-system-dns"></a>Domain Name System (DNS)
<a name="DNS"> </a>

Skype for Business Server 2015 erfordert aus den folgenden Gründen DNS:
  
- MIT DNS kann Skype for Business Server 2015 interne Server oder Pools ermitteln, was die Kommunikation zwischen Servern ermöglicht.
    
- MIT DNS können Clientcomputer den Front-End-Pool oder Standard Edition-Server ermitteln, der für SIP-Transaktionen verwendet wird.
    
- Sie ordnet einfache URLs für Konferenzen den Servern zu, die diese Konferenzen hosten.
    
- DNS ermöglicht externen Benutzern und Clientcomputern das Herstellen einer Verbindung mit Ihren Edgeservern oder dem HTTP-Reverseproxy für Chats oder Konferenzen.
    
- Damit können Unified Communications (UC)-Geräte, die nicht angemeldet sind, den Front-End-Pool oder Standard Edition-Server, auf dem der Geräteupdatewebdienst ausgeführt wird, ermitteln, um Updates zu erhalten und Protokolle zu senden.
    
- Die Verwendung von DNS ermöglicht mobilen Clients das automatische Ermitteln von Webdienstressourcen, ohne dass Benutzer manuell URLs in ihren Geräteeinstellungen eingeben müssen.
    
- Und wird beim DNS-Lastenausgleich verwendet.
    
Es ist wichtig zu beachten, dass Skype for Business Server 2015 keine internationalisierten Domänennamen (IDNs) unterstützt.
  
Und es ist äußerst wichtig zu beachten, dass jeder Name in DNS mit dem Computernamen identisch ist, der auf jedem Server konfiguriert ist, der von Skype for Business Server 2015 verwendet wird. Insbesondere dürfen in der Umgebung keine Kurznamen verwendet werden, und es müssen FQDNs für den Topologie-Generator verwendet werden.
  
Dies scheint für jeden Computer, der bereits einer Domäne beigetreten ist, logisch zu sein, aber wenn Sie über einen Edgeserver verfügen, der nicht mit Ihrer Domäne verbunden ist, hat er möglicherweise einen Kurznamen ohne Domänensuffix. Stellen Sie sicher, dass dies in diesem Fall nicht der Fall ist, weder im DNS noch auf dem Edgeserver oder einem Skype for Business Server 2015-Server oder -Pool.
  
Verwenden Sie auf jeden Fall keine Unicode-Zeichen oder Unterstriche. Standardzeichen (A-Z, a-z, 0-9 und Bindestriche) werden von externen DNS- und öffentlichen Zertifizierungsstelle unterstützt (Sie müssen dem SN im Zertifikat FQDNs zuweisen, vergessen Sie nicht), daher ersparen Sie sich viel Mühe, wenn Sie dies berücksichtigen.
  
Weitere Informationen zu den DNS-Anforderungen für Netzwerke finden Sie im Abschnitt ["Netzwerk"](../../plan-your-deployment/network-requirements/network-requirements.md) unserer Planungsdokumentation.
  
## <a name="certificates"></a>Zertifikate
<a name="Certs"> </a>

Eine der wichtigsten Dinge, die Sie vor der Bereitstellung tun können, ist sicherzustellen, dass Ihre Zertifikate in der Reihenfolge sind. Skype for Business Server 2015 benötigt eine Public Key Infrastructure (PKI) für Transport Layer Security (TLS) und MTLS (Mutual Transport Layer Security) Verbindungen. Im Wesentlichen verwendet Skype for Business Server Zertifikate, die von Zertifizierungsstelle ausgestellt wurden, um auf standardisierte Weise sicher zu kommunizieren.
  
Dies sind einige der Dinge, für die Skype for Business Server 2015 Zertifikate verwendet:
  
- TLS-Verbindungen zwischen Clients und Servern
    
- MTLS-Verbindungen zwischen Servern
    
- Partnerverbund mit automatischer DNS-Ermittlung von Partnern
    
- Zugriff von Remotebenutzern auf Sofortnachrichten
    
- Zugriff externer Benutzer auf Audio-/Videositzungen, Anwendungsfreigabe und Konferenzen
    
- Sprechen mit Webanwendungen und Outlook Web Access (OWA)
    
Daher ist die Zertifikatplanung ein Muss. Sehen wir uns nun eine Liste einiger Dinge an, die Sie beim Anfordern von Zertifikaten beachten müssen:
  
- Alle Serverzertifikate müssen die Serverautorisierung (Enhanced Key Usage [EKU], erweiterte Schlüsselverwendung für Server) unterstützen.
    
- Alle Serverzertifikate müssen einen Zertifikatsperrlisten-Verteilungspunkt unterstützen.
    
- Alle Zertifikate müssen mit einem Signaturalgorithmus signiert werden, der vom Betriebssystem unterstützt wird. Skype for Business Server 2015 unterstützt die SHA-1- und SHA-2-Suite mit Digestgrößen (224, 256, 384 und 512 Bit) und erfüllt oder übersteigt die Betriebssystemanforderungen.
    
- Die automatische Registrierung wird für interne Server mit Skype for Business Server 2015 unterstützt.
    
- Die automatische Registrierung wird für Skype for Business Server 2015-Edgeserver nicht unterstützt.
    
- Wenn Sie eine webbasierte Zertifikatanforderung an eine Windows Server 2003-Zertifizierungsstelle senden möchten, muss diese von einem Computer aus gesendet werden, auf dem entweder Windows Server 2003 mit SP2 oder Windows XP ausgeführt wird.
    
> [!NOTE]
> Obwohl KB922706 Unterstützung für die Behebung von Problemen bei der Registrierung von Webzertifikaten für eine Windows Server 2003-Zertifikatdienste-Webregistrierung bietet, ist es nicht möglich, Windows Server 2008, Windows Vista oder Windows 7 zum Anfordern eines Zertifikats von einer Windows Server 2003-Zertifizierungsstelle zu verwenden. 
  
> [!NOTE]
> Die Verwendung des RSASSA-PSS-Signaturalgorithmus wird nicht unterstützt und kann u. U. zu Fehlern bei der Anmeldung und anrufverteilten Problemen führen. 

> [!NOTE]
> Skype for Business Server 2015 unterstützt keine CNG-Zertifikate.
  
- Verschlüsselungsschlüssellängen von 1024, 2048 und 4096 werden unterstützt. Es wird eine Schlüssellänge von 2048 und höher empfohlen.
    
- Der Standardalgorithmus für Digest- oder Hashsignatur ist RSA. Die ECDH_P256, ECDH_P384 und ECDH_P521 werden ebenfalls unterstützt.
    
Das ist also eine Menge zu überlegen, und auf jeden Fall gibt es eine Vielzahl von Komfortniveaus beim Anfordern von Zertifikaten von einer Zertifizierungsstelle. Wir geben Ihnen weiter unten eine Anleitung, um Ihre Planung so schnell wie möglich zu gestalten.
  
### <a name="certificates-for-your-internal-servers"></a>Zertifikate für Ihre internen Server

Sie benötigen Zertifikate für die meisten internen Server, und höchstwahrscheinlich erhalten Sie sie von einer internen Zertifizierungsstelle (die sich in Ihrer Domäne befindet). Wenn Sie möchten, können Sie diese Zertifikate von einer externen Zertifizierungsstelle (die sich im Internet befindet) anfordern. Wenn Sie sich fragen, zu welcher öffentlichen Zertifizierungsstelle Sie wechseln sollten, können Sie die Liste der [Unified Communications-Zertifikatpartner](/SkypeForBusiness/certification/services-ssl) lesen.
  
Sie benötigen auch Zertifikate, wenn Skype for Business Server 2015 mit anderen Anwendungen und Servern kommuniziert, z. B. Microsoft Exchange Server. Dies muss natürlich ein Zertifikat sein, das diese anderen Apps und Server auf unterstützte Weise verwenden können. Skype for Business Server 2015 und andere Produkte von Microsoft unterstützen das Open Authorization (OAuth)-Protokoll für die Server-zu-Server-Authentifizierung und -Autorisierung. Wenn Sie daran interessiert sind, haben wir einen zusätzlichen Planungsartikel für OAuth und Skype for Business Server 2015.
  
Skype for Business Server 2015 bietet auch Unterstützung für (ohne Dass) Zertifikate, die mit der kryptografischen Sha-256-Hashfunktion signiert wurden. Zur Unterstützung des externen Zugriffs mithilfe von SHA-256 muss das externe Zertifikat von einer öffentlichen Zertifizierungsstelle mit SHA-256 ausgestellt werden.
  
Um die Dinge einfach zu halten, haben wir die Zertifikatanforderungen für Standard Edition-Server, Front-End-Pools und andere Rollen in die folgenden Tabellen übertragen, in denen die fiktive contoso.com als Beispiele verwendet wird (Wahrscheinlich verwenden Sie etwas anderes für Ihre Umgebung). Dies sind alle Standardwebserverzertifikate mit privaten Schlüsseln, die nicht exportiert werden können. Einige weitere Zu beachtende Dinge:
  
- Die erweiterte Serverschlüsselverwendung (EKU) wird automatisch konfiguriert, wenn Sie den Zertifikatassistenten zum Anfordern von Zertifikaten verwenden.
    
- Jeder Anzeigename des Zertifikats muss im Computerspeicher eindeutig sein.
    
- Wenn Sie sipinternal.contoso.com oder sipexternal.contoso.com in Ihrem DNS konfiguriert haben, müssen sie entsprechend den nachfolgenden Beispielnamen dem alternativen Subject Name (SAN) des Zertifikats hinzugefügt werden.
    
Zertifikate für Standard Edition-Server:
  
|**Zertifikat**|**Subject name/Common name**|**Alternativer Antragstellername**|**Beispiel**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|Standard  <br/> |FQDN des Pools  <br/> |FQDN des Pools und FQDN des Servers  <br/> Wenn mehrere SIP-Domänen vorhanden sind und die automatische Clientkonfiguration aktiviert wurde, erkennt der Zertifikat-Assistent die unterstützten FQDNs für SIP-Domänen und fügt diese hinzu.  <br/> Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich (Domain Name System) festgelegt ist, benötigen Sie auch Einträge für "sip.sipDomäne" (für jede vorhandene SIP-Domäne).  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com  <br/> Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch "SAN=sip.contoso.com; SAN=sip.fabrikam.com".  <br/> |Auf einem Standard Edition-Server entspricht der Server-FQDN dem Pool-FQDN.  <br/> Der Assistent erkennt alle SIP-Domänen, die Sie während des Setups angegeben haben, und fügt sie automatisch als alternative Betreffnamen hinzu.  <br/> Sie können dieses Zertifikat auch für die Server-zu-Server-Authentifizierung verwenden.  <br/> |
|Web, intern  <br/> |FQDN des Servers  <br/> |Jeder der folgenden:  <br/> • Interner Web-FQDN (identisch mit dem FQDN des Servers)  <br/> UND  <br/> • Erfüllen einfacher URLs  <br/> • Einfache EINWAHL-URL  <br/> • Einfache ADMIN-URL  <br/> ODER  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN=se01.contoso.com; SAN=se01.contoso.com; SAN= \* .contoso.com  <br/> |Sie können den internen Web-FQDN im Topologie-Generator nicht außer Kraft setzen.  <br/> Wenn Sie über mehrere einfache MEET-URLs verfügen, müssen Sie alle als SANs verwenden.  <br/> Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.  <br/> |
|Web, extern  <br/> |FQDN des Servers  <br/> |Jeder der folgenden:  <br/> • Externer Web-FQDN  <br/> UND  <br/> • Einfache EINWAHL-URL  <br/> • Erfüllen einfacher URLs pro SIP-Domäne  <br/> ODER  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN= \* .contoso.com  <br/> |Wenn Sie über mehrere einfache MEET-URLs verfügen, müssen Sie alle als alternative Betreffnamen verwenden.  <br/> Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.  <br/> |
   
Zertifikate für Front-End-Server in einem Front-End-Pool der Enterprise Edition:
  
|**Zertifikat**|**Subject name/Common name**|**Alternativer Antragstellername**|**Beispiel**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|Standard  <br/> |FQDN des Pools  <br/> |FQDN des Pools und FQDN des Servers  <br/> Wenn mehrere SIP-Domänen vorhanden sind und die automatische Clientkonfiguration aktiviert wurde, erkennt der Zertifikat-Assistent die unterstützten FQDNs für SIP-Domänen und fügt diese hinzu.  <br/> Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich (Domain Name System) festgelegt ist, benötigen Sie auch Einträge für "sip.sipDomäne" (für jede vorhandene SIP-Domäne).  <br/> |SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com  <br/> Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch "SAN=sip.contoso.com; SAN=sip.fabrikam.com".  <br/> |Der Assistent erkennt alle SIP-Domänen, die Sie während der Installation angegeben haben, und fügt sie dem alternativen Antragstellernamen (SAN) automatisch hinzu.  <br/> Sie können dieses Zertifikat auch für die Server-zu-Server-Authentifizierung verwenden.  <br/> |
|Web, intern  <br/> |FQDN des Pools  <br/> |Jeder der folgenden:  <br/> • Interner Web-FQDN (nicht identisch mit dem FQDN des Servers)  <br/> • Server-FQDN  <br/> • FQDN des Skype for Business-Pools  <br/> UND  <br/> • Erfüllen einfacher URLs  <br/> • Einfache EINWAHL-URL  <br/> • Einfache ADMIN-URL  <br/> ODER  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN= \* .contoso.com  <br/> |Wenn Sie über mehrere einfache MEET-URLs verfügen, müssen Sie alle als alternative Betreffnamen verwenden.  <br/> Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.  <br/> |
|Web, extern  <br/> |FQDN des Pools  <br/> |Jeder der folgenden:  <br/> • Externer Web-FQDN  <br/> UND  <br/> • Einfache EINWAHL-URL  <br/> • Einfache ADMIN-URL  <br/> ODER  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN= \* .contoso.com  <br/> |Wenn Sie über mehrere einfache MEET-URLs verfügen, müssen Sie alle als alternative Betreffnamen verwenden.  <br/> Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.  <br/> |
   
Zertifikate für den Director:
  
|**Zertifikat**|**Subject name/Common name**|**Alternativer Antragstellername**|**Beispiel**|
|:-----|:-----|:-----|:-----|
|Standard  <br/> |Directorpool  <br/> |FQDN des Director, FQDN des Directorpools.  <br/> Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien strenge DNS-Übereinstimmungen erforderlich sind, benötigen Sie auch Einträge für "sip.sipdomain" (für jede sip-Domäne, die Sie haben).  <br/> |pool.contoso.com; SAN=dir01.contoso.com  <br/> Wenn es sich bei diesem Director-Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch "SAN=sip.contoso.com; SAN=sip.fabrikam.com".  <br/> |
|Web, intern  <br/> |FQDN des Servers  <br/> |Jeder der folgenden:  <br/> • Interner Web-FQDN (identisch mit dem FQDN des Servers)  <br/> • Server-FQDN  <br/> • FQDN des Skype for Business-Pools  <br/> UND  <br/> • Erfüllen einfacher URLs  <br/> • Einfache EINWAHL-URL  <br/> • Einfache ADMIN-URL  <br/> ODER  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN=dir01.contoso.com; SAN=dir01.contoso.com SAN= \* .contoso.com  <br/> |
|Web, extern  <br/> |FQDN des Servers  <br/> |Jeder der folgenden:  <br/> • Externer Web-FQDN  <br/> UND  <br/> • Erfüllen einfacher URLs pro SIP-Domäne  <br/> • Einfache EINWAHL-URL  <br/> ODER  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |Der externe Web-FQDN des Director muss sich vom Front-End-Pool oder Front-End-Server unterscheiden.  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN= \* .contoso.com  <br/> |
   
Zertifikate für eigenständige Vermittlungsserver:
  
|**Zertifikat**|**Subject name/Common name**|**Alternativer Antragstellername**|**Beispiel**|
|:-----|:-----|:-----|:-----|
|Standard  <br/> |FQDN des Pools  <br/> |FQDN des Pools  <br/> FQDN des Poolmitgliedsservers  <br/> |SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net  <br/> |
   
Zertifikate für Survivable Branch Appliance:
  
|**Zertifikat**|**Subject name/Common name**|**Alternativer Antragstellername**|**Beispiel**|
|:-----|:-----|:-----|:-----|
|Standard  <br/> |FQDN der Appliance  <br/> |SIP.\<sipdomain\> (Sie benötigen nur einen Eintrag pro SIP-Domäne)  <br/> |SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-your-persistent-chat-server"></a>Zertifikate für ihren Server für beständigen Chat

Bei der Installation des Servers für beständigen Chat benötigen Sie ein Zertifikat, das von derselben Zertifizierungsstelle ausgestellt wurde, die auch von Ihren internen Skype for Business Server 2015-Servern verwendet wird. Dies muss für jeden Server ausgeführt werden, auf dem Webdienste für beständigen Chat für dateiupload/-download ausgeführt werden. Es wird dringend empfohlen, dass Sie über die erforderlichen Zertifikate verfügen, bevor Sie mit der Installation des beständigen Chats beginnen, und wenn Ihre Zertifizierungsstelle extern ist, noch mehr (dies kann einige Zeit dauern, bis sie ausgestellt werden).
  
### <a name="certificates-for-external-user-access-edge"></a>Zertifikate für den externen Benutzerzugriff (Edge)

Skype for Business Server 2015  unterstützt die Verwendung eines einzelnen öffentlichen Zertifikats für externe Zugriffs- und Webkonferenz-Edgeschnittstellen sowie den A/V-Authentifizierungsdienst, der alle über die Edgeserver bereitgestellt wird. Ihre interne Edgeschnittstelle verwendet in der Regel ein privates Zertifikat, das von Ihrer internen Zertifizierungsstelle ausgestellt wurde. Wenn es Ihnen lieber ist, können Sie auch hier ein öffentliches Zertifikat verwenden, wenn es von einer vertrauenswürdigen Zertifizierungsstelle kommt.
  
Ihr Reverseproxy (RP) verwendet auch ein öffentliches Zertifikat und verschlüsselt die Kommunikation zwischen Ihrer Rp und Clients sowie die Rp zu internen Servern mithilfe von HTTP (oder genauer: TLS über HTTP).
  
### <a name="certificates-for-mobility"></a>Zertifikate für Mobilität

Wenn Sie Mobilität bereitstellen und die automatische Ermittlung für mobile Clients unterstützen, müssen Sie einige zusätzliche Einträge für alternative Betreffnamen in Ihre Zertifikate eingeben, um die sicheren Verbindungen von den mobilen Clients zu unterstützen.
  
Welche Zertifizierungen? Sie benötigen für die automatische Ermittlung der Zertifikate hier san-Namen:
  
- Directorpool
    
- Front-End-Pool
    
- Reverse-Proxy
    
Wir listen die Besonderheiten in jeder tabelle unten auf.
  
Hier ist ein wenig Vorabplanung gut, aber manchmal haben Sie Skype for Business Server 2015 bereitgestellt, ohne die Mobilität bereitstellen zu wollen, und das kommt ganz nach unten, wenn Sie bereits über Zertifikate in Ihrer Umgebung verfügen. Das erneuten Ausstellen über eine interne Zertifizierungsstelle ist in der Regel recht einfach, aber bei öffentlichen Zertifikaten von einer öffentlichen Zertifizierungsstelle kann dies etwas teurer sein.
  
Wenn Sie sich dies genauer anschauen und über eine große Anzahl von SIP-Domänen verfügen (was das Hinzufügen von SANS verteuern würde), können Sie Ihren Reverseproxy so konfigurieren, dass http für die anfängliche AutoErmittlungsdienstanforderung anstelle von HTTPS (Standardkonfiguration) verwendet wird. Im Thema "Planen der Mobilität" finden Sie weitere Informationen dazu.
  
Zertifikatanforderungen für Directorpool und Front-End-Pool:
  
|**Beschreibung**|**Eintrag "SAN"**|
|:-----|:-----|
|URL des internen AutoErmittlungsdiensts  <br/> |SAN=lyncdiscoverinternal.\<sipdomain\>  <br/> |
|URL des externen AutoErmittlungsdiensts  <br/> |SAN=lyncdiscover.\<sipdomain\>  <br/> |
   
Alternativ können Sie SAN= \* verwenden.\<sipdomain\>
  
Anforderungen für Reverseproxyzertifikate (Public CA):
  
|**Beschreibung**|**Eintrag "SAN"**|
|:-----|:-----|
|URL des externen AutoErmittlungsdiensts  <br/> |SAN=lyncdiscover.\<sipdomain\>  <br/> |
   
Dieser SAN muss dem Zertifikat zugewiesen werden, das dem SSL-Listener auf dem Reverseproxy zugewiesen ist.
  
> [!NOTE]
> Der Reverseproxylistener wird SANs für die externen Webdienste-URL(en) haben. Einige Beispiele sind SAN=skypewebextpool01.contoso.com und dirwebexternal.contoso.com, wenn Sie den Director bereitgestellt haben (optional). 
  
## <a name="file-share"></a>Dateifreigabe
<a name="Fileshare"> </a>

Skype for Business Server 2015 kann dieselbe Dateifreigabe für alle Dateispeicher verwenden. Beachten Sie dabei Folgendes:
  
- Eine Dateifreigabe muss sich entweder im direkt angeschlossenen Speicher (DIRECT Attached Storage, DAS) oder in einem Speicherbereichsnetzwerk (Storage Area Network, SAN) befinden. Dies umfasst das verteilte Dateisystem (Distributed File System, DFS) sowie ein redundantes Array von unabhängigen Datenträgern (RAID) für Dateispeicher. Weitere Informationen zu DFS für Windows Server 2012 finden Sie auf [dieser DFS-Seite.](https://technet.microsoft.com/library/jj127250.aspx)
    
- Wir empfehlen einen freigegebenen Cluster für die Dateifreigabe. Wenn Sie eine verwenden, sollten Sie Windows Server 2012 oder Windows Server 2012 R2 clustern. Windows Server 2008 R2 ist ebenfalls akzeptabel. Warum das neueste Windows? Ältere Versionen verfügen möglicherweise nicht über die richtigen Berechtigungen zum Aktivieren aller Features. Sie können den Clusteradministrator zum Erstellen [](https://support.microsoft.com/help/224967/how-to-create-file-shares-on-a-cluster) der Dateifreigaben verwenden, und dieser Artikel zum Erstellen von Dateifreigaben in einem Cluster hilft Ihnen bei diesen Details.
    
> [!CAUTION] 
> Sie sollten wissen, dass die Verwendung von NAS (Network Attached Storage) als Dateifreigabe nicht unterstützt wird. Verwenden Sie daher eine der oben aufgeführten Optionen. 
  
