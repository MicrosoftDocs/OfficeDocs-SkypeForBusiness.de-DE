---
title: Anforderungen an die Umgebung für Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4812c444-2546-48d7-9ca7-b71fce508ed8
description: 'Zusammenfassung: Konfigurieren Sie Ihre nicht-Server Anforderungen für Skype for Business Server 2015. Es gibt eine Reihe von Dingen, die Sie konfigurieren möchten, bevor Sie Ihre Bereitstellung ausführen, einschließlich Active Directory, DNS, certs und Dateifreigaben.'
ms.openlocfilehash: 3e0c53d73da71e4ada89c95a6438b62dd2507872
ms.sourcegitcommit: 5ec5df597614d402917e0585575dd69acda22172
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2019
ms.locfileid: "36253925"
---
# <a name="environmental-requirements-for-skype-for-business-server-2015"></a>Environmental requirements for Skype for Business Server 2015
 
**Zusammenfassung:** Konfigurieren Sie Ihre nicht-Server Anforderungen für Skype for Business Server 2015. Es gibt eine Reihe von Dingen, die Sie konfigurieren möchten, bevor Sie Ihre Bereitstellung ausführen, einschließlich Active Directory, DNS, certs und Dateifreigaben.
  
Was ist eine Umwelt Anforderung für Skype for Business Server 2015? Nun, wir haben alles, was nicht direkt mit dem Server in Verbindung steht, in dieses Thema gesetzt, damit Sie nicht so viel klicken müssen. Wenn Sie nach Server Voraussetzungen suchen, lesen Sie die [Server Anforderungen für Skype for Business Server 2015](server-requirements.md) doc. die[Netzwerkplanung](../../plan-your-deployment/network-requirements/network-requirements.md) wird ebenfalls separat dokumentiert. Andernfalls haben wir das in diesem Artikel:
  
- [Active Directory](environmental-requirements.md#AD)
  
- [Domain Name System (DNS)](environmental-requirements.md#DNS)
  
- [Zertifikate](environmental-requirements.md#Certs)
  
- [Dateifreigabe](environmental-requirements.md#Fileshare)
  
## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

Während viele Konfigurationsdaten für Server und Dienste im zentralen Verwaltungsspeicher von Skype for Business Server 2015 gespeichert sind, gibt es noch einige Dinge, die in Active Directory gespeichert sind:
  
|**Active Directory-Objekte**|**Objekttypen**|
|:-----|:-----|
|Schemaerweiterungen  <br/> |Benutzerobjekterweiterungen  <br/> |
||Erweiterungen für lync Server 2013 und lync Server 2010, um die Abwärtskompatibilität mit den vorherigen unterstützten Versionen zu gewährleisten.  <br/> |
|Daten  <br/> |Der Benutzer-SIP-URI und andere Einstellungen  <br/> |
||Kontaktobjekte für Anwendungen (wie die reaktionsgruppenanwendung und die Anwendung Conferencing Attendant).  <br/> |
||Für die Abwärtskompatibilität veröffentlichte Daten.  <br/> |
||Einen Dienst Kontrollpunkt (Service Control Point, SCP) für den zentralen Verwaltungsspeicher.  <br/> |
||Das Kerberos-Authentifizierungskonto (ein optionales Computerobjekt).  <br/> |
   
### <a name="os-for-domain-controllers"></a>Betriebssysteme für Domänencontroller

Welches Betriebssystem für Domänencontroller kann verwendet werden? Hier die Liste:

- Windows Server 2019
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
Nun müssen die Domänenfunktionsebene jeder Domäne, in der Sie Skype for Business Server 2015 bereitstellen, und die Gesamtstruktur-Funktionsebene einer beliebigen Gesamtstruktur, in der Sie Skype for Business Server 2015 bereitstellen, eine der folgenden sein:

- Windows Server 2019
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
- Windows Server 2003
    
Dürfen in diesen Umgebungen schreibgeschützte Domänencontroller vorhanden sein? Sicher, solange auch nicht schreibgeschützte Domänencontroller verfügbar sind.
  
Nun ist es wichtig zu wissen, dass Skype for Business Server 2015 keine Single-Labeling-Domains unterstützt. Was ist das? Wenn Sie über eine Stammdomäne mit der Bezeichnung "contoso. local" verfügen, wird das in Ordnung sein. Wenn Sie über eine Stammdomäne verfügen, die nur den Namen local hat, wird dies nicht funktionieren und wird daher nicht unterstützt. Ein wenig mehr dazu wurde [in diesem Knowledge Base-Artikel](https://support.microsoft.com/kb/300684/en-us)geschrieben.
  
Skype for Business Server 2015 unterstützt auch keine Umbenennung von Domänen. Wenn Sie das wirklich zu tun haben, müssen Sie Skype for Business Server 2015 deinstallieren, die Domäne umbenennen und dann Skype for Business Server 2015 erneut installieren.
  
Schließlich handelt es sich möglicherweise um eine Domäne mit einer gesperrten AD DS-Umgebung, und das ist in Ordnung. Wir haben weitere Informationen dazu, wie Sie Skype for Business Server 2015 in dieser Art von Umgebung in den Bereitstellungs Dokumentationen bereitstellen können.
  
### <a name="ad-topologies"></a>AD-Topologien

Die unterstützten Topologien von Skype for Business Server 2015 sind:
  
- Einzelne Gesamtstruktur mit einzelner Domäne
    
- Einzelne Gesamtstruktur mit einer Struktur und mehreren Domänen
    
- Einzelne Gesamtstruktur mit mehreren Strukturen und nicht zusammenhängenden Namespaces
    
- Mehrere Gesamtstrukturen in einer Topologie mit zentraler Gesamtstruktur
    
- Mehrere Gesamtstrukturen in einer Topologie mit Ressourcengesamtstruktur
    
- Mehrere Gesamtstrukturen in einer Skype for Business-Ressourcengesamtstruktur-Topologie mit Exchange Online
    
- Mehrere Gesamtstrukturen in einer Topologie mit Ressourcengesamtstruktur mit Skype for Business Online und Azure Active Directory Connect
    
Wir verfügen über Diagramme und Beschreibungen, mit denen Sie ermitteln können, welche Topologie in Ihrer Umgebung vorhanden ist, oder was Sie vor der Installation von Skype for Business Server 2015 einrichten müssen. Um es einfach zu halten, werden wir auch einen Schlüssel einbeziehen:
  
![Schlüssel zu den Symbolen, die für Skype for Business-Topologiediagramme verwendet werden](../../media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>Einzelne Gesamtstruktur mit einzelner Domäne

![Diagramm einer einzelnen Active-Directory-Gesamtstruktur mit einer einzigen Domäne](../../media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
Einfacher geht es nicht, es handelt sich um eine einzelne Domänengesamtstruktur, die eine gemeinsame Topologie ist.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>Einzelne Gesamtstruktur mit einer Struktur und mehreren Domänen

![Diagramm mit einer einzigen Gesamtstruktur, einer einzelnen Struktur und mehreren Domänen](../../media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
Dieses Diagramm zeigt erneut eine einzelne Gesamtstruktur, es gibt aber auch eine oder mehrere untergeordnete Domänen (in diesem konkreten Beispiel gibt es drei). Die Domäne, in der die Benutzer erstellt werden, unterscheidet sich möglicherweise von der Domäne, in der Skype for Business Server 2015 bereitgestellt wird. Warum sollten Sie sich Sorgen machen? Beachten Sie, dass bei der Bereitstellungeines Skype for Business Server-Front-End-Pools alle Server in diesem Pool eine einzige Domäne aufweisen müssen. Sie können über eine domänenübergreifende Verwaltung über die Unterstützung von Windows universelle Administratorgruppen durch den Skype for Business Server verfügen.
  
Zurück zum obigen Diagramm können Sie sehen, dass Benutzer aus einer Domäne in der Lage sind, auf Skype for Business Server-Pools aus der gleichen Domäne oder aus unterschiedlichen Domänen zuzugreifen, selbst wenn diese Benutzer in einer untergeordneten Domäne sind.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>Einzelne Gesamtstruktur mit mehreren Strukturen und nicht zusammenhängenden Namespaces

![Diagramm mit einer einzigen Gesamtstruktur, mehreren Strukturen und getrennten Namespaces](../../media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
Es kann sein, dass Sie eine Topologie haben, die mit diesem Diagramm vergleichbar ist, in der Sie über eine Gesamtstruktur verfügen, aber innerhalb dieser Gesamtstruktur mehrere Domänen mit separaten AD-Namespaces sind. Wenn das der Fall ist, ist dieses Diagramm eine gute Illustration, denn wir haben Benutzer in drei verschiedenen Domänen, die auf Skype for Business Server 2015 zugreifen. Durchgezogene Linien weisen darauf hin, dass Sie in ihrer eigenen Domäne auf einen Skype for Business-Server Pool zugreifen, während eine gestrichelte Linie angibt, dass Sie in einem anderen Baum zu einem Pool wechseln.
  
Wie Sie sehen können, können Benutzer derselben Domäne, derselben Struktur, aber auch einer anderen Struktur erfolgreich auf Pools zugreifen.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>Mehrere Gesamtstrukturen in einer Topologie mit zentraler Gesamtstruktur

![Diagramm mit mehreren Gesamtstrukturen in einer Topologie mit zentraler Gesamtstruktur](../../media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype for Business Server 2015 unterstützt mehrere Gesamtstrukturen, die in einer zentralen Gesamtstrukturtopologie konfiguriert sind. Wenn Sie nicht sicher sind, was Sie haben, verwendet die zentrale Gesamtstruktur in der Topologie Objekte, um Benutzer in den anderen Gesamtstrukturen darzustellen, und hostet Benutzerkonten für alle Benutzer in der Gesamtstruktur.
  
Wie funktioniert das? Nun, ein Verzeichnis Synchronisierungs Produkt (wie Forefront Identity Manager oder FIM) verwaltet die Benutzerkonten Ihrer Organisation während Ihres gesamten Bestehens. Wenn ein Konto erstellt oder in der Gesamtstruktur gelöscht wird, wird diese Änderung im entsprechenden Kontakt in der zentralen Gesamtstruktur synchronisiert.
  
Wenn Ihre Anzeigen Infrastruktur in der Lage ist, in diese Topologie zu wechseln, ist es ganz klar nicht einfach, aber wenn Sie bereits vorhanden sind oder Ihre Gesamtstruktur Infrastruktur planen, kann dies eine gute Wahl sein. Sie können Ihre Skype for Business Server 2015-Bereitstellung in einer einzigen Gesamtstruktur zentralisieren, während Benutzer in jeder Gesamtstruktur suchen, kommunizieren und die Anwesenheit anderer Benutzer anzeigen können. Alle Benutzer Kontakt Updates werden automatisch mit der Synchronisierungssoftware verarbeitet.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Mehrere Gesamtstrukturen in einer Skype for Business-Ressourcengesamtstruktur-Topologie
<a name="BKMK_multipleforestopology"> </a>

![Diagramm mit mehreren Gesamtstrukturen in einer Topologie mit Ressourcengesamtstruktur](../../media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
Eine Ressourcengesamtstrukturtopologie wird ebenfalls unterstützt. Hier wird eine Gesamtstruktur für die Ausführung ihrer Serveranwendungen wie Microsoft Exchange Server und Skype for Business Server 2015 bereitgestellt. Diese Ressourcengesamtstrukturen hosten auch eine synchronisierte Darstellung von aktiven Benutzerobjekten, jedoch keine Anmelde fähigen Benutzerkonten. Die Ressourcengesamtstruktur ist also eine Umgebung mit freigegebenen Diensten für andere Gesamtstrukturen, in der sich die Benutzerobjekte befinden, und Sie verfügen über eine Vertrauensstellung auf Gesamtstrukturebene mit der Ressourcengesamtstruktur.
  
Beachten Sie, dass Exchange Server in derselben Ressourcengesamtstruktur wie Skype for Business Server oder in einer anderen Gesamtstruktur bereitgestellt werden kann.
  
Zur Bereitstellung von Skype for Business Server 2015 in dieser Art von Topologie erstellen Sie für jedes Benutzerkonto in den Benutzergesamtstrukturen ein deaktiviertes Benutzerobjekt in der Ressourcengesamtstruktur (wenn sich Microsoft Exchange Server bereits in der Umgebung befindet, ist dies möglicherweise für Sie erledigt). Dann benötigen Sie ein Verzeichnissynchronisierungstool (wie Forefront Identity Manager oder FIM), um Benutzerkonten über ihren Lebenszyklus zu verwalten.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Mehrere Gesamtstrukturen in einer Skype for Business-Ressourcengesamtstruktur-Topologie mit Exchange Online
<a name="BKMK_multipleforestopology"> </a>

Diese Topologie ähnelt der Topologie, die unter [Mehrere Gesamtstrukturen in einer Skype for Business-Ressourcengesamtstruktur-Topologie](environmental-requirements.md#BKMK_multipleforestopology) beschrieben wird.
  
In dieser Topologie gibt es eine oder mehrere Benutzergesamtstrukturen, und Skype for Business Server wird in einer dedizierten Ressourcengesamtstruktur bereitgestellt. Exchange Server kann lokal in derselben Ressourcengesamtstruktur oder in einer anderen Gesamtstruktur bereitgestellt und für hybride mit Exchange Online konfiguriert werden, oder e-Mail-Dienste können ausschließlich von Exchange Online für die lokalen Konten bereitgestellt werden. Für diese Topologie steht kein Diagramm zur Verfügung.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Mehrere Gesamtstrukturen in einer Topologie mit Ressourcengesamtstruktur mit Skype for Business Online und Azure Active Directory Connect
<a name="BKMK_multipleforestopology"> </a>

![Zeigt zwei AD-Gesamtstrukturen, eine Benutzergesamtstruktur und eine Ressourcengesamtstruktur an. Die beiden Gesamtstrukturen haben eine Vertrauensstellung und sind mit Office 365 unter Verwendung von Azure AD Connect synchronisiert. Alle Benutzer sind für Skype for Business über Office 365 aktiviert.](../../media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
Bei diesem Szenario sind mehrere lokale Gesamtstrukturen mit einer Topologie mit Ressourcengesamtstruktur vorhanden. Zwischen den Active Directory-Gesamtstrukturen besteht eine vollständige Vertrauensstellung. Das Tool „Azure Active Directory Connect“ wird zur Synchronisierung von Konten zwischen den lokalen Benutzergesamtstrukturen und Office 365 verwendet.
  
 Die Organisation verfügt auch über Office 365 und verwendet [Azure Active Directory Connect](https://go.microsoft.com/fwlink/p/?LinkId=614836) , um Ihre lokalen Konten mit Office 365 zu synchronisieren. Benutzer, die für Skype for Business aktiviert sind, werden über Office 365 und Skype for Business Online aktiviert. Skype for Business Server wird nicht lokal bereitgestellt.
  
Die Authentifizierung für einmaliges Anmelden wird von einer Active Directory-Verbunddienst Farm bereitgestellt, die sich in der Benutzergesamtstruktur befindet.
  
In diesem Szenario wird die Bereitstellung von Exchange lokal, Exchange Online, einer hybriden Exchange-Lösung oder die Bereitstellung von Exchange überhaupt nicht unterstützt. (Das Diagramm zeigt nur lokal Exchange, aber auch die anderen Exchange-Lösungen werden vollständig unterstützt.)
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>Mehrere Gesamtstrukturen in einer Topologie mit Ressourcengesamtstruktur mit Skype for Business-Hybridbereitstellung
<a name="BKMK_multipleforestopology"> </a>

In diesem Szenario gibt es eine oder mehrere lokale Benutzergesamtstrukturen, und Skype for Business wird in einer dedizierten Ressourcengesamtstruktur bereitgestellt und für den Hybrid Modus mit Skype for Business Online konfiguriert. Exchange Server kann lokal in der gleichen Ressourcengesamtstruktur oder in einer anderen Gesamtstruktur bereitgestellt werden und kann für hybride mit Exchange Online konfiguriert werden. Alternativ können e-Mail-Dienste ausschließlich von Exchange Online für die lokalen Konten bereitgestellt werden.
  
Weitere Informationen finden Sie unter [Konfigurieren einer Multi-Forest-Umgebung für Hybrid-Skype for Business](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md).
  
## <a name="domain-name-system-dns"></a>DNS (Domain Name System)
<a name="DNS"> </a>

Skype for Business Server 2015 erfordert DNS, und zwar aus folgenden Gründen:
  
- DNS ermöglicht es Skype for Business Server 2015, interne Server oder Pools zu erkennen, was eine Server-zu-Server-Kommunikation ermöglicht.
    
- Mit DNS können Clientcomputer den Front-End-Pool oder Standard Edition-Server ermitteln, der für SIP-Transaktionen verwendet wird.
    
- Es ordnet einfache URLs für Konferenzen den Servern zu, auf denen diese Konferenzen gehostet werden.
    
- DNS ermöglicht es externen Benutzern und Clientcomputern, eine Verbindung mit Ihren Edge-Servern oder dem HTTP-Reverseproxy für Sofortnachrichten (im) oder Konferenzen herzustellen.
    
- Mit dieser Option können Unified Communications (UC)-Geräte, die nicht angemeldet sind, den Front-End-Pool oder den Standard Edition-Server ermitteln, auf dem der Geräte Update-Webdienst ausgeführt wird, um Updates zu erhalten und Protokolle zu senden.
    
- Die Verwendung von DNS ermöglicht mobilen Clients die automatische Ermittlung von Webdienstressourcen, ohne dass Benutzer in den Geräteeinstellungen manuell URLs eingeben müssen.
    
- Außerdem wird es im DNS-Lastenausgleich verwendet.
    
Es ist wichtig zu beachten, dass Skype for Business Server 2015 keine Internationalisierungs Domänennamen (IDNs) unterstützt.
  
Und es ist äußerst wichtig, daran zu erinnern, dass jeder Name in DNS mit dem Computernamen identisch ist, der auf jedem Server konfiguriert ist, der von Skype for Business Server 2015 verwendet wird. Insbesondere können wir keine Kurznamen in der Umgebung haben und FQDNs für den Topologie-Generator aufweisen.
  
Dies scheint so zu sein, als wäre es für jeden Computer, der bereits einer Domäne beigetreten ist, logisch, doch wenn Sie über einen Edgeserver verfügen, der nicht zu Ihrer Domäne gehört, ist möglicherweise ein Standardname mit einem kurzen Namen ohne Domänensuffix vorhanden. Stellen Sie sicher, dass dies nicht der Fall ist, entweder in DNS oder auf dem Edgeserver oder einem beliebigen Skype for Business Server 2015-Server oder-Pool.
  
Und definitiv keine Unicode-Zeichen oder Unterstriche verwenden. Standard Zeichen (also a-z, a-z, 0-9 und Bindestriche) sind diejenigen, die von externen DNS-und öffentlichen Zertifizierungsstellen unterstützt werden (Sie müssen dem SN im Zertifikat FQDNs zuweisen, vergessen Sie nicht), damit Sie sich viel Kummer ersparen, wenn Sie nennen dies im Hinterkopf.
  
Weitere Informationen zu den DNS-Anforderungen für Networking entnehmen Sie dem Abschnitt [Networking](../../plan-your-deployment/network-requirements/network-requirements.md) unserer Planungsdokumentation.
  
## <a name="certificates"></a>Zertifikate
<a name="Certs"> </a>

Stellen Sie vor der Bereitstellung unbedingt sicher, dass Ihre Zertifikate in Ordnung sind. Skype for Business Server 2015 benötigt eine Public Key-Infrastruktur (PKI) für Transport Layer Security (TLS) und MTLS-Verbindungen (Mutual Transport Layer Security). Um in standardisierter Weise sicher zu kommunizieren, verwendet Skype for Business Server Zertifikate, die von Zertifizierungsstellen ausgestellt wurden.
  
Dies sind einige der Dinge, für die Skype for Business Server 2015 Zertifikate verwendet:
  
- TLS-Verbindungen zwischen Client und Server
    
- MTLS-Verbindungen zwischen Servern
    
- Partnerverbund mit automatischer DNS-Ermittlung von Partnern
    
- Zugriff von Remotebenutzern auf Sofortnachrichten
    
- Zugriff externer Benutzer auf AV-Sitzungen, Anwendungsfreigabe und Konferenzen
    
- Unterhaltungen mit Webanwendungen und Outlook Web Access (OWA)
    
Daher ist die Zertifikatplanung ein muss. Sehen wir uns nun eine Liste mit einigen der Dinge an, die Sie beim Anfordern von Zertifikaten beachten müssen:
  
- Alle Serverzertifikate müssen die Serverautorisierung (Enhanced Key Usage [EKU], erweiterte Schlüsselverwendung für Server) unterstützen.
    
- Alle Serverzertifikate müssen einen Zertifikatsperrlisten-Verteilungspunkt unterstützen.
    
- Alle Zertifikate müssen mithilfe eines Signaturalgorithmus signiert werden, der vom Betriebssystem unterstützt wird. Skype for Business Server 2015 unterstützt die SHA-1-und SHA-2-Suite von Digest-Größen (224, 256, 384 und 512-Bit) und erfüllt oder überschreitet die Anforderungen des Betriebssystems.
    
- Die automatische Registrierung wird für interne Server unterstützt, auf denen Skype for Business Server 2015 ausgeführt wird.
    
- Die automatische Registrierung wird für Skype for Business Server 2015 Edge-Server nicht unterstützt.
    
- Wenn Sie eine webbasierte Zertifikatanforderung an eine Windows Server 2003-Zertifizierungsstelle übermitteln, müssen Sie Sie von einem Computer übermitteln, auf dem Windows Server 2003 mit SP2 oder Windows XP ausgeführt wird.
    
> [!NOTE]
> Obwohl mit Update KB922706 Probleme beim Registrieren von Webzertifikaten für eine Windows Server 2003-Zertifikatdienste-Webregistrierung behoben werden können, ist es mit diesem Update nicht möglich, unter Windows Server 2008, Windows Vista oder Windows 7 ein Zertifikat bei einer Windows Server 2003-Zertifizierungsstelle anzufordern. 
  
> [!NOTE]
> Die Verwendung des Signaturalgorithmus RSASSA-PSS wird nicht unterstützt und kann unter anderem zu Fehlern bei der Anmeldung und Problemen mit der Anrufweiterleitung führen.  
  
- Es werden Verschlüsselungsschlüssellängen von 1.024, 2.048 und 4.096 Bit unterstützt. Empfohlen werden Schlüssellängen ab 2.048 Bit.
    
- Der standardmäßige Digest- bzw. Hashsignaturalgorithmus ist RSA. Die Algorithmen ECDH_P256, ECDH_P384 und ECDH_P521 werden ebenfalls unterstützt.
    
Das ist also viel zu überlegen und auf jeden Fall gibt es eine Reihe von Komfortstufen, bei denen Zertifikate von einer Zertifizierungsstelle angefordert werden. Nachfolgend finden Sie einige weitere Anleitungen, die Ihnen helfen, Ihre Planung so schmerzlos wie möglich zu gestalten.
  
### <a name="certificates-for-your-internal-servers"></a>Zertifikate für Ihre internen Server

Sie benötigen Zertifikate für die meisten internen Server, und Sie erhalten Sie höchstwahrscheinlich von einer internen Zertifizierungsstelle (die sich in Ihrer Domäne befindet). Wahlweise können Sie diese Zertifikate von einer externen Zertifizierungsstelle (aus dem Internet) erhalten. Wenn Sie sich Fragen, zu welcher öffentlichen Zertifizierungsstelle Sie wechseln sollten, sehen Sie sich die Liste der [Unified Communications-Zertifikat Partner](/SkypeForBusiness/certification/services-ssl) an.
  
Außerdem benötigen Sie Zertifikate, wenn Skype for Business Server 2015 mit anderen Anwendungen und Servern wie Microsoft Exchange Server kommuniziert. Dies muss offensichtlich ein Zertifikat sein, das von den anderen Anwendungen und Servern unterstützt wird. Skype for Business Server 2015 und andere Microsoft-Produkte unterstützen das Open Authorization (OAuth)-Protokoll für die Server-zu-Server-Authentifizierung und-Autorisierung. Wenn Sie daran interessiert sind, haben wir einen zusätzlichen Planungsartikel für OAuth und Skype for Business Server 2015.
  
Skype for Business Server 2015 enthält auch Unterstützung für (ohne erforderlich) Zertifikate, die mit der SHA-256-kryptografischen Hashfunktion signiert wurden. Um den externen Zugriff mithilfe von SHA-256 zu unterstützen, muss das externe Zertifikat von einer öffentlichen Zertifizierungsstelle unter Verwendung von SHA-256 ausgestellt werden.
  
Um zu versuchen, die Dinge einfach zu halten, haben wir die Zertifikatanforderungen für Standard Edition-Server, Front-End-Pools und andere Rollen in den folgenden Tabellen zusammengestellt, wobei die fiktiven contoso.com-Beispiele verwendet werden (wahrscheinlich verwenden Sie etwas andere für Ihre Umgebung). Hierbei handelt es sich um alle standardmäßigen Webserverzertifikate mit privaten Schlüsseln, die nicht exportierbar sind. Weitere Hinweise:
  
- Die erweiterte Schlüsselverwendung (Enhanced Key Usage, EKU) für Server wird automatisch konfiguriert, wenn Sie den Zertifikat-Assistenten zum Anfordern von Zertifikaten verwenden.
    
- Der Anzeigename jedes Zertifikats muss im Computerspeicher eindeutig sein.
    
- Wenn Sie sipinternal.contoso.com oder sipexternal.contoso.com in Ihrem DNS konfiguriert haben, müssen Sie gemäß den folgenden Beispiel Namen zum alternativen Namen (Subject Name, San) des Zertifikats hinzugefügt werden.
    
Zertifikate für Standard Edition-Server:
  
|**Zertifikat**|**Antragstellername/Allgemeiner Name**|**Alternativer Antragstellername**|**Beispiel**|**Anmerkungen**|
|:-----|:-----|:-----|:-----|:-----|
|Standard  <br/> |FQDN des Pools  <br/> |FQDN des Pools und FQDN des Servers  <br/> Wenn mehrere SIP-Domänen vorhanden sind und die automatische Clientkonfiguration aktiviert wurde, erkennt der Zertifikat-Assistent die unterstützten FQDNs für SIP-Domänen und fügt diese hinzu.  <br/> Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich (Domain Name System) festgelegt ist, benötigen Sie auch Einträge für „sip.sipDomäne“ (für jede vorhandene SIP-Domäne).  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com  <br/> Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch „SAN=sip.contoso.com; SAN=sip.fabrikam.com“.  <br/> |Auf Standard Edition-Servern ist der Server-FQDN mit dem FQDN des Pools identisch.  <br/> Der Assistent erkennt alle SIP-Domänen, die Sie während der Installation angegeben haben, und fügt sie automatisch zum alternativen Antragstellernamen (SAN) hinzu.  <br/> Sie können dieses Zertifikat auch für die Server-zu-Server-Authentifizierung verwenden.  <br/> |
|Web, intern  <br/> |FQDN des Servers  <br/> |Jeder der folgenden:  <br/> • Interner Web-FQDN (entspricht dem FQDN des Servers)  <br/> UND  <br/> • Einfache URLs erfüllen  <br/> • Einfache URL für Einwahl  <br/> • Einfache Administrator-URL  <br/> ODER  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN = SE01. contoso. com; San = SE01. contoso. com; San =\*. contoso.com  <br/> |Sie können den internen Web-FQDN im Topologie-Generator nicht außer Kraft setzen.  <br/> Wenn Sie über mehrere einfache Besprechungs-URLs verfügen, müssen Sie alle als alternative Antragstellernamen einbeziehen.  <br/> Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.  <br/> |
|Web, extern  <br/> |FQDN des Servers  <br/> |Jeder der folgenden:  <br/> • Externer Web-FQDN  <br/> UND  <br/> • Einfache URL für Einwahl  <br/> • Einfache URLs pro SIP-Domäne erfüllen  <br/> ODER  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN = SE01. contoso. com; San = webcon01. contoso. com; San =\*. contoso.com  <br/> |Wenn Sie über mehrere einfache URLs für Besprechungen verfügen, müssen Sie Sie alle als Alternativen Betreff-Namen einbeziehen.  <br/> Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.  <br/> |
   
Zertifikate für Front-End-Server in einem Front-End-Pool:
  
|**Zertifikat**|**Antragstellername/Allgemeiner Name**|**Alternativer Antragstellername**|**Beispiel**|**Anmerkungen**|
|:-----|:-----|:-----|:-----|:-----|
|Standard  <br/> |FQDN des Pools  <br/> |FQDN des Pools und FQDN des Servers  <br/> Wenn mehrere SIP-Domänen vorhanden sind und die automatische Clientkonfiguration aktiviert wurde, erkennt der Zertifikat-Assistent die unterstützten FQDNs für SIP-Domänen und fügt diese hinzu.  <br/> Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich (Domain Name System) festgelegt ist, benötigen Sie auch Einträge für „sip.sipDomäne“ (für jede vorhandene SIP-Domäne).  <br/> |SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com   <br/> Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch „SAN=sip.contoso.com; SAN=sip.fabrikam.com“.  <br/> |Der Assistent erkennt alle SIP-Domänen, die Sie während der Installation angegeben haben, und fügt sie automatisch zum alternativen Antragstellernamen (SAN) hinzu.  <br/> Sie können dieses Zertifikat auch für die Server-zu-Server-Authentifizierung verwenden.  <br/> |
|Web, intern  <br/> |FQDN des Pools  <br/> |Jeder der folgenden:  <br/> • Interner Web-FQDN (der nicht mit dem FQDN des Servers identisch ist)  <br/> • Server-FQDN  <br/> • Skype for Business-Pool-FQDN  <br/> UND  <br/> • Einfache URLs erfüllen  <br/> • Einfache URL für Einwahl  <br/> • Einfache Administrator-URL  <br/> ODER  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN = ee01. contoso. com; San = ee01. contoso. com; San =\*. contoso.com  <br/> |Wenn Sie über mehrere einfache URLs für Besprechungen verfügen, müssen Sie Sie alle als Alternativen Betreff-Namen einbeziehen.  <br/> Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.  <br/> |
|Web, extern  <br/> |FQDN des Pools  <br/> |Jeder der folgenden:  <br/> • Externer Web-FQDN  <br/> UND  <br/> • Einfache URL für Einwahl  <br/> • Einfache Administrator-URL  <br/> ODER  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN = ee01. contoso. com; San = webcon01. contoso. com; San =\*. contoso.com  <br/> |Wenn Sie über mehrere einfache URLs für Besprechungen verfügen, müssen Sie Sie alle als Alternativen Betreff-Namen einbeziehen.  <br/> Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.  <br/> |
   
Zertifikate für den Direktor:
  
|**Zertifikat**|**Antragstellername/Allgemeiner Name**|**Alternativer Antragstellername**|**Beispiel**|
|:-----|:-----|:-----|:-----|
|Standard  <br/> |Directorpool  <br/> |FQDN des Directors, FQDN des Director-Pools.  <br/> Wenn dieser Pool der Server für die automatische Anmeldung für Clients ist und strenge DNS-Übereinstimmungen in Gruppenrichtlinien erforderlich sind, benötigen Sie auch Einträge für SIP. sipdomain (für jede SIP-Domäne, die Sie haben).  <br/> |pool.contoso.com; SAN=dir01.contoso.com   <br/> Wenn dieser Director-Pool der Server für die automatische Anmeldung für Clients ist und in Gruppenrichtlinien strikter DNS-Abgleich erforderlich ist, benötigen Sie auch San = SIP. contoso. com; San = SIP. fabrikam. com  <br/> |
|Web, intern  <br/> |FQDN des Servers  <br/> |Jeder der folgenden:  <br/> • Interner Web-FQDN (entspricht dem FQDN des Servers)  <br/> • Server-FQDN  <br/> • Skype for Business-Pool-FQDN  <br/> UND  <br/> • Einfache URLs erfüllen  <br/> • Einfache URL für Einwahl  <br/> • Einfache Administrator-URL  <br/> ODER  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN = dir01. contoso. com; San = dir01. contoso. com San =\*. contoso.com  <br/> |
|Web, extern  <br/> |FQDN des Servers  <br/> |Jeder der folgenden:  <br/> • Externer Web-FQDN  <br/> UND  <br/> • Einfache URLs pro SIP-Domäne erfüllen  <br/> • Einfache URL für Einwahl  <br/> ODER  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |Der FQDN des Director External Web muss vom Front-End-Pool oder Front-End-Server abweichen.  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN = dir01. contoso. com; San = directorwebcon01. contoso. com San =\*. contoso.com  <br/> |
   
Zertifikate für eigenständigen Vermittlungs Server:
  
|**Zertifikat**|**Antragstellername/Allgemeiner Name**|**Alternativer Antragstellername**|**Beispiel**|
|:-----|:-----|:-----|:-----|
|Standard  <br/> |FQDN des Pools  <br/> |FQDN des Pools  <br/> FQDN des Poolmitgliedsservers  <br/> |SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net  <br/> |
   
Zertifikate für Survivable Branch Appliance:
  
|**Zertifikat**|**Antragstellername/Allgemeiner Name**|**Alternativer Antragstellername**|**Beispiel**|
|:-----|:-----|:-----|:-----|
|Standard  <br/> |FQDN der Anwendung  <br/> |SIP. \<sipdomain\> (Sie benötigen nur einen Eintrag pro SIP-Domäne)  <br/> |SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-your-persistent-chat-server"></a>Zertifikate für Ihren Server für beständigen Chat

Wenn Sie Ihren beständigen Chat Server installieren, benötigen Sie ein Zertifikat, das von der gleichen Zertifizierungsstelle ausgestellt wird, die von ihren internen Servern für Skype for Business Server 2015 verwendet wird. Dies muss für jeden Server erfolgen, auf dem die beständigen Chat-Webdienste für Datei Upload/-Download ausgeführt werden. Wir empfehlen dringend, dass Sie über die erforderlichen Zertifikate verfügen, bevor Sie mit der Installation des beständigen Chats beginnen, und wenn Ihre Zertifizierungsstelle extern ist (diese Dinge können etwas Zeit in Anspruch nehmen).
  
### <a name="certificates-for-external-user-access-edge"></a>Zertifikate für den Zugriff externer Benutzer (Edge)

Skype for Business Server 2015 unterstützt die Verwendung eines **einzigen öffentlichen Zertifikats** für Access-und Webkonferenz-Edge-externe Schnittstellen sowie den a/V-Authentifizierungsdienst, der alle über die Edgeserver (s) bereitgestellt wird. Ihre Edge-interne Schnittstelle verwendet normalerweise ein privates Zertifikat, das von ihrer internen Zertifizierungsstelle ausgestellt wurde, Sie können aber auch ein öffentliches Zertifikat verwenden, wenn es von einer vertrauenswürdigen Zertifizierungsstelle ist.
  
Ihr Reverseproxy (RP) wird ebenfalls ein öffentliches Zertifikat verwenden und es verschlüsselt die Kommunikation zwischen Ihrem Reverseproxy und den Clients sowie zwischen dem Reverseproxy und den internen Servern mithilfe von HTTP (oder präziser: TLS über HTTP).
  
### <a name="certificates-for-mobility"></a>Zertifikate für Mobilität

Wenn Sie Mobilität bereitstellen und die automatische Ermittlung für mobile Clients unterstützen, müssen Sie für Ihre Zertifikate einige zusätzliche Alternative Namen Einträge für Subjekte hinzufügen, um die sicheren Verbindungen von den mobilen Clients zu unterstützen.
  
Welche Zertifikate? Sie benötigen alternative Antragstellernamen für die automatische Erkennung auf Zertifikaten:
  
- Directorpool
    
- Front-End-Pool
    
- Reverseproxy
    
Die Besonderheiten sind in allen Tabellen unten aufgelistet.
  
In diesem Fall ist eine kleine Vorplanung gut, aber manchmal haben Sie Skype for Business Server 2015 bereitgestellt, ohne dass Sie die Mobilität bereitstellen möchten, und das kommt auf dem laufenden, wenn Sie bereits über Zertifikate in Ihrer Umgebung verfügen. Eine erneute Veröffentlichung über eine interne Zertifizierungsstelle ist in der Regel ziemlich einfach, aber mit öffentlichen Zertifikaten einer öffentlichen Zertifizierungsstelle, die etwas teurer sein kann.
  
Wenn Sie dies sehen, und wenn Sie über viele SIP-Domänen verfügen (wodurch das Hinzufügen von Sans teurer wird), können Sie Ihren Reverse-Proxy so konfigurieren, dass er http für die anfängliche AutoErmittlungsdienst Anforderung verwendet, anstatt HTTPS zu verwenden (Dies ist die Standardeinstellung Konfiguration). Im Abschnitt „Planen der Mobilität“ finden Sie ausführlichere Informationen dazu.
  
Zertifikatanforderungen für Director Pool und Front-End-Pool:
  
|**Beschreibung**|**SAN-Eintrag**|
|:-----|:-----|
|Interne URL des AutoErmittlungsdiensts  <br/> |San = lyncdiscoverinternal. \<sipdomain\>  <br/> |
|URL des externen AutoErmittlungsdiensts  <br/> |San = lyncdiscover. \<sipdomain\>  <br/> |
   
Sie können auch San =\*verwenden. \<sipdomain\>
  
Reverseproxy-Zertifikatsanforderungen (öffentliche ZS):
  
|**Beschreibung**|**SAN-Eintrag**|
|:-----|:-----|
|URL des externen AutoErmittlungsdiensts  <br/> |San = lyncdiscover. \<sipdomain\>  <br/> |
   
Dieser SAN muss dem Zertifikat zugewiesen werden, das dem SSL-Listener (Secure Sockets Layer) auf dem Reverseproxy zugewiesen ist.
  
> [!NOTE]
> Der Listener des Reverse-Proxys wird Sans für Ihre externen Webdienste-URL (s) haben. Einige Beispiele sind San = skypewebextpool01. contoso. com und dirwebexternal.contoso.com, wenn Sie den Director bereitgestellt haben (Dies ist optional). 
  
## <a name="file-share"></a>Dateifreigabe
<a name="Fileshare"> </a>

Skype for Business Server 2015 kann dieselbe Dateifreigabe für alle Dateispeicher verwenden. Beachten Sie bitte Folgendes:
  
- Eine Dateifreigabe muss sich entweder auf DAS (Direct Attached Storage) oder auf einem SAN (Storage Area Network) befinden, einschließlich des DFS (Distributed File System) sowie von RAID-Komponenten (Redundant Array of Independent Disks) für Dateispeicher. Weitere Informationen zu DFS für Windows Server 2012 finden Sie auf [dieser DFS-Seite](https://technet.microsoft.com/en-us/library/jj127250.aspx).
    
- Wir empfehlen einen freigegebenen Cluster für die Dateifreigabe. Wenn Sie eine verwenden, sollten Sie Windows Server 2012 oder Windows Server 2012 R2 gruppieren. Windows Server 2008 R2 ist ebenfalls akzeptabel. Warum die neuesten Windows-Version? Ältere Versionen verfügen möglicherweise nicht über die erforderlichen Berechtigungen, um alle Features zu aktivieren. Sie können die Clusterverwaltung verwenden, um die Dateifreigaben zu erstellen, und das [Erstellen von Dateifreigaben in einem Cluster](https://support.microsoft.com/en-us/help/224967/how-to-create-file-shares-on-a-cluster) Artikel wird Ihnen bei diesen Details helfen.
    
> [!CAUTION] 
> Beachten Sie, dass Network Attached Storage (NAS) als Dateifreigabe nicht unterstützt wird. Verwenden Sie daher eine der oben genannten Optionen. 
  

