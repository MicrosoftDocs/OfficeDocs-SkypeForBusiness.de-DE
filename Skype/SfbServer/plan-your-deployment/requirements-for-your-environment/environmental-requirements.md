---
title: Umgebungsanforderungen für Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Zusammenfassung: Konfigurieren Sie Ihre nicht-Server Anforderungen für Skype for Business Server 2015. Es gibt eine Vielzahl von Dingen, die Sie vor der Bereitstellung konfigurieren möchten, einschließlich Active Directory, DNS, certs und Filesharings.'
ms.openlocfilehash: 00b7828cfc06dd9d0ea1d7097580c9c25317e95a
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790287"
---
# <a name="environmental-requirements-for-skype-for-business-server-2015"></a>Umgebungsanforderungen für Skype for Business Server 2015
 
**Zusammenfassung:** Konfigurieren Sie Ihre nicht-Server Anforderungen für Skype for Business Server 2015. Es gibt eine Vielzahl von Dingen, die Sie vor der Bereitstellung konfigurieren möchten, einschließlich Active Directory, DNS, certs und Filesharings.
  
Was ist eine Umgebungs Anforderung für Skype for Business Server 2015? Nun, wir haben alles, was nicht direkt Server ist, in dieses Thema aufgenommen, sodass Sie nicht so viel klicken müssen. Wenn Sie nach Server Voraussetzungen suchen, können Sie die [Server Anforderungen für Skype for Business Server 2015](server-requirements.md) doc. die [Netzwerkplanung](../../plan-your-deployment/network-requirements/network-requirements.md) ist ebenfalls separat dokumentiert. Andernfalls ist dies das, was wir in diesem Artikel erhalten haben:
  
- [Active Directory](environmental-requirements.md#AD)
  
- [Domain Name System (DNS)](environmental-requirements.md#DNS)
  
- [Zertifikate](environmental-requirements.md#Certs)
  
- [Dateifreigabe](environmental-requirements.md#Fileshare)
  
## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

Während viele Konfigurationsdaten für Server und Dienste im zentralen Verwaltungsspeicher von Skype for Business Server 2015 gespeichert werden, werden einige Dinge noch in Active Directory gespeichert:
  
|**Active Directory-Objekte**|**Objekttypen**|
|:-----|:-----|
|Schemaerweiterungen  <br/> |Benutzerobjekterweiterungen  <br/> |
||Erweiterungen für lync Server 2013 und lync Server 2010, um die Abwärtskompatibilität mit den vorherigen unterstützten Versionen aufrechtzuerhalten.  <br/> |
|Daten  <br/> |SIP-URI des Benutzers und andere Benutzereinstellungen  <br/> |
||Kontaktobjekte für Anwendungen (wie Reaktionsgruppenanwendung und Konferenzzentrale).  <br/> |
||Daten werden aus Gründen der Abwärtskompatibilität veröffentlicht.  <br/> |
||Einen Dienststeuerungspunkt (Service Control Points, SCP) für den zentralen Verwaltungsspeicher.  <br/> |
||Kerberos-Authentifizierungs Konto (ein optionales Computerobjekt).  <br/> |
   
### <a name="os-for-domain-controllers"></a>Betriebssystem für Domänencontroller

Welches Domänen Controller-Betriebssystem kann verwendet werden? Wir haben die folgende Liste:

- Windows Server 2019 (Sie müssen Skype for Business Server 2015 Kumulatives Update 5 oder höher haben)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
Nun müssen die Domänenfunktionsebene jeder Domäne, in der Sie Skype for Business Server 2015 bereitstellen, und die Gesamtstrukturfunktionsebene einer Gesamtstruktur, in der Sie Skype for Business Server 2015 bereitstellen, eine der folgenden sein:

- Windows Server 2019 (Sie müssen Skype for Business Server 2015 Kumulatives Update 5 oder höher haben)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
- Windows Server 2003
    
Können in diesen Umgebungen schreibgeschützte Domänencontroller vorhanden sein? Sicher, solange auch schreibbare Domänencontroller am selben Standort wie der Skype for Business Server verfügbar sind.
  
Nun ist es wichtig zu wissen, dass Skype for Business Server 2015 keine Single-labeld Domains unterstützt. Was sind sie? Wenn Sie über eine Stammdomäne mit dem Namen "contoso. local" verfügen, wird das gut gehen. Wenn Sie über eine Stammdomäne verfügen, die nur local heißt, funktioniert das nicht, und es wird daher nicht unterstützt. Ein wenig mehr dazu wurde [in diesem Knowledge Base-Artikel](https://support.microsoft.com/kb/300684/en-us)geschrieben.
  
Skype for Business Server 2015 unterstützt auch nicht das Umbenennen von Domänen. Wenn Sie das wirklich tun müssen, müssen Sie Skype for Business Server 2015 deinstallieren, die Domänenumbenennung durchführen und dann Skype for Business Server 2015 erneut installieren.
  
Schließlich haben Sie möglicherweise mit einer Domäne mit einer gesperrten AD DS Umgebung zu tun, und das ist in Ordnung. Weitere Informationen zum Bereitstellen von Skype for Business Server 2015 in dieser Art von Umgebung finden Sie in den Bereitstellungsdokumenten.
  
### <a name="ad-topologies"></a>AD-Topologien

Die unterstützten Topologien von Skype for Business Server 2015 sind:
  
- Einzelne Gesamtstruktur mit einzelner Domäne
    
- Einzelne Gesamtstruktur mit einer Struktur und mehreren Domänen
    
- Einzelne Gesamtstruktur mit mehreren Strukturen und nicht zusammenhängenden Namespaces
    
- Mehrere Gesamtstrukturen in einer Topologie mit zentraler Gesamtstruktur
    
- Mehrere Gesamtstrukturen in einer Topologie mit Ressourcengesamtstruktur
    
- Mehrere Gesamtstrukturen in einer Topologie mit Skype for Business Ressourcengesamtstruktur mit Exchange Online
    
- Mehrere Gesamtstrukturen in einer Topologie mit Ressourcengesamtstruktur mit Skype for Business Online und Azure Active Directory Connect
    
Wir verfügen über Diagramme und Beschreibungen, mit denen Sie ermitteln können, welche Topologie in Ihrer Umgebung vorhanden ist, oder was Sie vor der Installation von Skype for Business Server 2015 möglicherweise einrichten müssen. Um es einfach zu halten, werden wir auch einen Schlüssel einschließen:
  
![Der ist ein Schlüssel zu den Symbolen, die für Skype for Business Topologie-Diagramme verwendet werden.](../../media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>Einzelne Gesamtstruktur mit einzelner Domäne

![Diagramm Active Directory einzelnen Gesamtstruktur mit einer einzelnen Domäne](../../media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
Es wird nicht einfacher als dies, es handelt sich um eine einzelne Domänengesamtstruktur, dies ist eine allgemeine Topologie.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>Einzelne Gesamtstruktur mit einer Struktur und mehreren Domänen

![Diagramm für eine einzelne Gesamtstruktur, eine einzelne Struktur und mehreren Domänen](../../media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
Dieses Diagramm zeigt wieder eine einzelne Gesamtstruktur, aber Sie hat auch eine oder mehrere untergeordnete Domänen (es gibt drei in diesem spezifischen Beispiel). Die Domäne, in der die Benutzer erstellt werden, unterscheidet sich möglicherweise von der Domäne, in der Skype for Business Server 2015 bereitgestellt wird. Warum sollten Sie sich darüber Gedanken machen? Beachten Sie, dass bei der Bereitstellungeines Skype for Business Server Front-End-Pool alle Server in diesem Pool sich in einer einzigen Domäne befinden müssen. Sie können eine domänenübergreifende Verwaltung über die Unterstützung von Skype for Business Server von Windows-universellen Administratorgruppen haben.
  
Im obigen Diagramm sehen Sie, dass Benutzer aus einer Domäne auf Skype for Business Server Pools aus derselben oder aus unterschiedlichen Domänen zugreifen können, selbst wenn sich diese Benutzer in einer untergeordneten Domäne befinden.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>Einzelne Gesamtstruktur mit mehreren Strukturen und nicht zusammenhängenden Namespaces

![Diagramm für eine einzelne Gesamtstruktur, mehrere Strukturen und nicht zusammenhängende Namespaces](../../media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
Es kann sein, dass Sie eine Topologie haben, die dem Diagramm ähnelt, in dem Sie eine Gesamtstruktur haben, in dieser Gesamtstruktur jedoch mehrere Domänen mit separaten AD-Namespaces vorhanden sind. Wenn dies der Fall ist, ist dieses Diagramm eine gute Illustration, da wir Benutzer in drei verschiedenen Domänen haben, die auf Skype for Business Server 2015 zugreifen. Durchgezogene Linien deuten darauf hin, dass Sie auf einen Skype for Business Server Pool in ihrer eigenen Domäne zugreifen, während eine gestrichelte Linie angibt, dass Sie in einen Pool in einer anderen Struktur wechseln.
  
Wie Sie sehen können, können Benutzer in der gleichen Domäne, in der gleichen Struktur oder sogar in einer anderen Struktur erfolgreich auf Pools zugreifen.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>Mehrere Gesamtstrukturen in einer Topologie mit zentraler Gesamtstruktur

![Mehrere Gesamtstrukturen in einem Topologie-Diagramm der zentralen Gesamtstruktur](../../media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype for Business Server 2015 unterstützt mehrere Gesamtstrukturen, die in einer Topologie mit zentraler Gesamtstruktur konfiguriert sind. Wenn Sie sich nicht sicher sind, was Sie haben, verwendet die zentrale Gesamtstruktur in der Topologie Objekte, um Benutzer in den anderen Gesamtstrukturen darzustellen, und hostet Benutzerkonten für alle Benutzer in der Gesamtstruktur.
  
Wie funktioniert das? Nun, ein Verzeichnis Synchronisierungs Produkt (beispielsweise Forefront Identity Manager oder FIM) verwaltet die Benutzerkonten Ihrer Organisation während Ihres gesamten Bestehens. Wenn ein Konto aus einer Gesamtstruktur erstellt oder gelöscht wird, wird diese Änderung mit dem entsprechenden Kontakt in der zentralen Gesamtstruktur synchronisiert.
  
Wenn Ihre AD-Infrastruktur direkt in diese Topologie verschoben wird, ist dies möglicherweise nicht einfach, aber wenn Sie bereits vorhanden sind oder Ihre Gesamtstruktur Infrastruktur planen, kann dies eine gute Wahl sein. Sie können Ihre Skype for Business Server 2015-Bereitstellung in einer einzelnen Gesamtstruktur zentralisieren, während Benutzer in jeder Gesamtstruktur suchen, kommunizieren und das vorhanden sein anderer Benutzer anzeigen können. Alle Benutzer Kontakt Updates werden automatisch mit der Synchronisierungssoftware verarbeitet.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Mehrere Gesamtstrukturen in einer Skype for Business-Ressourcengesamtstruktur-Topologie
<a name="BKMK_multipleforestopology"> </a>

![Mehrere Gesamtstrukturen in einem Topologie-Diagramm der Ressourcengesamtstruktur](../../media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
Außerdem wird eine Topologie mit Ressourcengesamtstruktur unterstützt. Hier wird eine Gesamtstruktur für die Ausführung ihrer Serveranwendungen wie Exchange Server und Skype for Business Server 2015 dediziert. Diese Ressourcengesamtstrukturen hosten auch eine synchronisierte Darstellung von aktiven Benutzerobjekten, jedoch keine Anmelde aktivierten Benutzerkonten. Die Ressourcengesamtstruktur ist also eine Umgebung für gemeinsame Dienste für andere Gesamtstrukturen, in der sich die Benutzerobjekte befinden, und Sie verfügen über eine Vertrauensstellung auf Gesamtstrukturebene mit der Ressourcengesamtstruktur.
  
Beachten Sie, dass Exchange Server in derselben Ressourcengesamtstruktur wie Skype for Business Server oder in einer anderen Gesamtstruktur bereitgestellt werden können.
  
Wenn Sie Skype for Business Server 2015 in dieser Art von Topologie bereitstellen möchten, erstellen Sie ein deaktiviertes Benutzerobjekt in der Ressourcengesamtstruktur für jedes Benutzerkonto in den Benutzergesamtstrukturen (wenn sich Exchange Server bereits in der Umgebung befindet, ist dies möglicherweise für Sie erledigt). Anschließend benötigen Sie ein Verzeichnissynchronisierungstool (wie Forefront Identity Manager oder FIM), um Benutzerkonten über ihren Lebenszyklus zu verwalten.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Mehrere Gesamtstrukturen in einer Topologie mit Skype for Business Ressourcengesamtstruktur mit Exchange Online
<a name="BKMK_multipleforestopology"> </a>

Diese Topologie ähnelt der in [mehreren Gesamtstrukturen in einer Skype for Business-Ressourcengesamtstruktur-Topologie](environmental-requirements.md#BKMK_multipleforestopology)beschriebenen Topologie.
  
In dieser Topologie gibt es eine oder mehrere Benutzergesamtstrukturen, und Skype for Business Server wird in einer dedizierten Ressourcengesamtstruktur bereitgestellt. Exchange Server können lokal in derselben Ressourcengesamtstruktur oder in einer anderen Gesamtstruktur bereitgestellt und für hybridbereitstellung mit Exchange Online konfiguriert werden, oder e-Mail-Dienste können ausschließlich von Exchange Online für die lokalen Konten bereitgestellt werden. Für diese Topologie ist kein Diagramm verfügbar.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Mehrere Gesamtstrukturen in einer Topologie mit Ressourcengesamtstruktur mit Skype for Business Online und Azure Active Directory Connect
<a name="BKMK_multipleforestopology"> </a>

![Zeigt zwei AD-Gesamtstrukturen, eine Benutzergesamtstruktur und eine Ressourcengesamtstruktur. Die beiden Gesamtstrukturen haben eine Vertrauensstellung. Sie werden mit Microsoft 365 oder Office 365 mit Azure AD Connect synchronisiert. Alle Benutzer sind für Skype for Business über Microsoft 365 oder Office 365 aktiviert.](../../media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
In diesem Szenario gibt es mehrere Gesamtstrukturen mit einer Topologie mit einer Ressourcengesamtstruktur. Zwischen den Active Directory Gesamtstrukturen besteht eine voll vertrauenswürdige Beziehung. Das Azure Active Directory Connect-Tool wird zum Synchronisieren von Konten zwischen den lokalen Benutzergesamtstrukturen und Microsoft 365 oder Office 365 verwendet.
  
 Die Organisation verfügt außerdem über Microsoft 365 oder Office 365 und verwendet [Azure Active Directory Connect](https://go.microsoft.com/fwlink/p/?LinkId=614836) , um Ihre lokalen Konten mit Microsoft 365 oder Office 365 zu synchronisieren. Benutzer, die für Skype for Business aktiviert sind, sind über Microsoft 365 oder Office 365 und Skype for Business Online aktiviert. Skype for Business Server wird nicht lokal bereitgestellt.
  
Die Authentifizierung mit einmaligem Anmelden wird von einer Active Directory Verbunddienst Farm bereitgestellt, die sich in der Benutzergesamtstruktur befindet.
  
In diesem Szenario wird es unterstützt, Exchange lokal, Exchange Online, eine hybride Exchange-Lösung bereitzustellen oder überhaupt keine Exchange-Bereitstellung zu haben. (Das Diagramm zeigt nur lokale Exchange-Bereitstellung, aber auch die anderen Exchange-Lösungen werden vollständig unterstützt.)
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>Mehrere Gesamtstrukturen in einer Topologie mit Ressourcengesamtstruktur mit Hybrid Skype for Business
<a name="BKMK_multipleforestopology"> </a>

In diesem Szenario gibt es eine oder mehrere lokale Benutzergesamtstrukturen, und Skype for Business wird in einer dedizierten Ressourcengesamtstruktur bereitgestellt und für den Hybrid Modus mit Skype for Business Online konfiguriert. Exchange Server können lokal in derselben Ressourcengesamtstruktur oder in einer anderen Gesamtstruktur bereitgestellt werden und können für hybride mit Exchange Online konfiguriert werden. Alternativ können e-Mail-Dienste ausschließlich von Exchange Online für die lokalen Konten bereitgestellt werden.
  
Weitere Informationen finden Sie unter [Konfigurieren einer Umgebung mit mehreren Gesamtstrukturen für Hybrid Skype for Business](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md).
  
## <a name="domain-name-system-dns"></a>Domain Name System (DNS)
<a name="DNS"> </a>

Für Skype for Business Server 2015 ist DNS aus folgenden Gründen erforderlich:
  
- Mithilfe von DNS können Skype for Business Server 2015 interne Server oder Pools ermitteln, sodass eine Server-zu-Server-Kommunikation möglich ist.
    
- DNS ermöglicht Clientcomputern, die Front-End-Pool oder Standard Edition-Server zu ermitteln, die für SIP-Transaktionen verwendet werden.
    
- Es ordnet einfache URLs für Konferenzen mit den Servern zu, die diese Konferenzen hosten.
    
- Mit DNS können externe Benutzer und Clientcomputer eine Verbindung mit ihren Edgeserver oder dem HTTP-Reverseproxy für Chatnachrichten oder Konferenzen herstellen.
    
- Mit dieser Option können Unified Communications-Geräte (UC), die nicht angemeldet sind, die Front-End-Pool oder Standard Edition-Server, auf dem der Geräte Update-Webdienst installiert ist, zum Abrufen von Updates und Senden von Protokollen ermitteln.
    
- Durch die Verwendung von DNS können mobile Clients automatisch Webdienste-Ressourcen ermitteln, ohne dass Benutzer in ihren Geräteeinstellungen manuell URLs eingeben müssen.
    
- Und wird im DNS-Lastenausgleich verwendet.
    
Beachten Sie, dass Skype for Business Server 2015 keine internationalen Domänennamen (IDNs) unterstützt.
  
Und es ist äußerst wichtig, daran zu denken, dass jeder Name im DNS mit dem Computernamen identisch ist, der auf jedem von Skype for Business Server 2015 verwendeten Server konfiguriert ist. Insbesondere dürfen keine Kurznamen in der Umgebung vorhanden sein, und es müssen FQDNs für den Topologie-Generator vorhanden sein.
  
Dies scheint logisch für alle Computer zu sein, die bereits einer Domäne beigetreten sind, aber wenn Sie über eine Edgeserver verfügen, die nicht mit Ihrer Domäne verbunden ist, kann die Standardeinstellung ein kurzer Name ohne Domänensuffix sein. Stellen Sie sicher, dass dies nicht der Fall ist, weder in DNS noch im Edgeserver oder auf einem Skype for Business Server 2015 Server oder Pool.
  
Und verwenden Sie definitiv keine Unicode-Zeichen oder Unterstriche. Standard Zeichen (a-z, a-z, 0-9 und Bindestriche) werden von externen DNS-und öffentlichen Zertifizierungsstellen unterstützt (Sie müssen dem SN im Zertifikat FQDNs zuweisen, vergessen Sie nicht), damit Sie sich viel Kummer ersparen, wenn Sie dies im Hinterkopf behalten.
  
Weitere Informationen zu den DNS-Anforderungen für Netzwerke finden Sie im Abschnitt [Networking](../../plan-your-deployment/network-requirements/network-requirements.md) in unserer Planungsdokumentation.
  
## <a name="certificates"></a>Zertifikate
<a name="Certs"> </a>

Eines der wichtigsten Dinge, die Sie vor der Bereitstellung tun können, ist sicherzustellen, dass Ihre Zertifikate ordnungsgemäß sind. Skype for Business Server 2015 benötigt eine Public Key-Infrastruktur (PKI) für TLS (Transport Layer Security) und MTLS-Verbindungen (Mutual Transport Layer Security). Um eine standardisierte sichere Kommunikation sicherzustellen, verwendet Skype for Business Server Zertifikate, die von Zertifizierungsstellen ausgestellt wurden.
  
Dies sind einige der Dinge, für die Skype for Business Server 2015 Zertifikate verwendet:
  
- TLS-Verbindungen zwischen Clients und Servern
    
- MTLS-Verbindungen zwischen Servern
    
- Partnerverbund mit automatischer DNS-Ermittlung von Partnern
    
- Zugriff von Remotebenutzern auf Sofortnachrichten
    
- Zugriff externer Benutzer auf Audio/Video-Sitzungen (AV), Anwendungsfreigabe und Konferenzen
    
- Im Gespräch mit Webanwendungen und-Outlook Web Access (OWA)
    
Die Zertifikatplanung ist daher ein muss. Nun sehen wir uns eine Liste mit einigen Dingen an, die Sie beim Anfordern von Zertifikaten beachten müssen:
  
- Alle Serverzertifikate müssen die Serverautorisierung (Enhanced Key Usage [EKU], erweiterte Schlüsselverwendung für Server) unterstützen.
    
- Alle Serverzertifikate müssen einen Zertifikatsperrlisten-Verteilungspunkt unterstützen.
    
- Alle Zertifikate müssen mit einem vom Betriebssystemunter stützten Signaturalgorithmus signiert werden. Skype for Business Server 2015 unterstützt die SHA-1-und SHA-2-Suite mit Digest-Größen (224, 256, 384 und 512-Bit) und erfüllt oder überschreitet die Betriebssystemanforderungen.
    
- Die automatische Registrierung wird für interne Server mit Skype for Business Server 2015 unterstützt.
    
- Die automatische Registrierung wird für Skype for Business Server 2015-Edge-Server nicht unterstützt.
    
- Wenn Sie eine webbasierte Zertifikatanforderung an eine Windows Server 2003-Zertifizierungsstelle senden möchten, muss diese von einem Computer aus gesendet werden, auf dem entweder Windows Server 2003 mit SP2 oder Windows XP ausgeführt wird.
    
> [!NOTE]
> Obwohl KB922706 Unterstützung für die Lösung von Problemen bei der Registrierung von webzertifikaten für eine Windows Server 2003-Zertifikatdienste-Webregistrierung bietet, ist es nicht möglich, Windows Server 2008, Windows Vista oder Windows 7 zum Anfordern eines Zertifikats von einer Windows Server 2003 Zertifizierungsstelle zu verwenden. 
  
> [!NOTE]
> Die Verwendung des Signaturalgorithmus RSASSA-PSS wird nicht unterstützt und kann unter anderem zu Fehlern bei Anmelde-und Anruf Weiterleitungs Problemen führen. 

> [!NOTE]
> CNG-Zertifikate werden von Skype for Business Server 2015 nicht unterstützt.
  
- Die Verschlüsselungsschlüssel Längen 1024, 2048 und 4096 werden unterstützt. Die Schlüssellängen von 2048 und höher werden empfohlen.
    
- Der standardmäßige Digest-oder Hashsignatur Algorithmus ist RSA. Die ECDH_P256-, ECDH_P384-und ECDH_P521 Algorithmen werden ebenfalls unterstützt.
    
Das ist also eine Menge zu denken, und auf jeden Fall gibt es eine Vielzahl von Komfort Ebenen mit dem Anfordern von Zertifikaten von einer Zertifizierungsstelle. Im folgenden erhalten Sie weitere Anleitungen, um Ihre Planung so schmerzlos wie möglich zu gestalten.
  
### <a name="certificates-for-your-internal-servers"></a>Zertifikate für Ihre internen Server

Sie benötigen Zertifikate für die meisten internen Server, und höchstwahrscheinlich erhalten Sie diese von einer internen Zertifizierungsstelle (die sich in Ihrer Domäne befindet). Wenn Sie möchten, können Sie diese Zertifikate von einer externen Zertifizierungsstelle anfordern (eine im Internet befindliche). Wenn Sie sich Fragen, welche öffentliche Zertifizierungsstelle Sie besuchen sollten, können Sie die Liste [Unified Communications Zertifikat Partner](/SkypeForBusiness/certification/services-ssl) Auschecken.
  
Außerdem benötigen Sie Zertifikate, wenn Skype for Business Server 2015 mit anderen Anwendungen und Servern wie Exchange Server kommuniziert. Dies muss natürlich ein Zertifikat sein, das diese anderen apps und Server auf unterstützte Weise verwenden können. Skype for Business Server 2015 und andere Microsoft-Produkte unterstützen das Open Authorization (OAuth)-Protokoll für die Server-zu-Server-Authentifizierung und-Autorisierung. Wenn Sie an diesem Thema interessiert sind, haben wir einen zusätzlichen Planungsartikel für OAuth und Skype for Business Server 2015.
  
Skype for Business Server 2015 enthält auch Unterstützung für (ohne erforderliche) Zertifikate, die mit der kryptografischen Hashfunktion von SHA-256 signiert wurden. Um den externen Zugriff mithilfe von SHA-256 zu unterstützen, muss das externe Zertifikat von einer öffentlichen Zertifizierungsstelle mit SHA-256 ausgestellt werden.
  
Um die Dinge unkompliziert zu halten, haben wir die Zertifikatanforderungen für Standard Edition-Server, Front-End-Pools und andere Rollen in den folgenden Tabellen formuliert, wobei die fiktive Contoso.com als Beispiele verwendet wird (Sie verwenden wahrscheinlich etwas anderes für Ihre Umgebung). Hierbei handelt es sich um alle standardmäßigen Webserverzertifikate mit privaten Schlüsseln, die nicht exportierbar sind. Einige zusätzliche Dinge, die Sie beachten sollten:
  
- Die erweiterte Schlüsselverwendung (Enhanced Key Usage, EKU) von Servern wird automatisch konfiguriert, wenn Sie den Zertifikat-Assistenten zum Anfordern von Zertifikaten verwenden.
    
- Jeder Zertifikatanzeige Name muss im Computerspeicher eindeutig sein.
    
- Wenn Sie sipinternal.contoso.com oder sipexternal.contoso.com in Ihrem DNS konfiguriert haben, müssen Sie gemäß den folgenden Beispiel Namen zum alternativen Antragstellernamen (San) des Zertifikats hinzugefügt werden.
    
Zertifikate für Standard Edition-Server:
  
|**Zertifikat**|**Antragstellername/Allgemeiner Name**|**Alternativer Antragstellername**|**Beispiel**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|Standard  <br/> |FQDN des Pools  <br/> |FQDN des Pools und FQDN des Servers  <br/> Wenn mehrere SIP-Domänen vorhanden sind und die automatische Clientkonfiguration aktiviert wurde, erkennt der Zertifikat-Assistent die unterstützten FQDNs für SIP-Domänen und fügt diese hinzu.  <br/> Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich (Domain Name System) festgelegt ist, benötigen Sie auch Einträge für "sip.sipDomäne" (für jede vorhandene SIP-Domäne).  <br/> |SN = SE01. contoso. com; San = SE01. contoso. com  <br/> Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch "SAN=sip.contoso.com; SAN=sip.fabrikam.com".  <br/> |Auf einem Standard Edition-Server entspricht der Server-FQDN dem Pool-FQDN.  <br/> Der Assistent erkennt alle SIP-Domänen, die Sie während des Setups angegeben haben, und fügt Sie automatisch als Alternative Antragstellernamen hinzu.  <br/> Sie können dieses Zertifikat auch für die Server-zu-Server-Authentifizierung verwenden.  <br/> |
|Web, intern  <br/> |FQDN des Servers  <br/> |Jeder der folgenden:  <br/> • Interner FQDN des Webs (entspricht dem FQDN des Servers)  <br/> UND  <br/> • Einfache URLs erfüllen  <br/> • Einfache URL für Einwahl  <br/> • Einfache admin-URL  <br/> ODER  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |SN = SE01. contoso. com; San = SE01. contoso. com; San = Meet. contoso. com; San = Meet. fabrikam. com; San = dialin. contoso. com; San = admin. contoso. com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN = SE01. contoso. com; San = SE01. contoso. com; San = \* . contoso.com  <br/> |Sie können den internen webfqdn im Topologie-Generator nicht außer Kraft setzen.  <br/> Wenn Sie über mehrere einfache URLs verfügen, müssen Sie alle als Sans einschließen.  <br/> Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.  <br/> |
|Web, extern  <br/> |FQDN des Servers  <br/> |Jeder der folgenden:  <br/> • Externer FQDN des Webs  <br/> UND  <br/> • Einfache URL für Einwahl  <br/> • Erfüllen einfacher URLs pro SIP-Domäne  <br/> ODER  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |SN = SE01. contoso. com; San = webcon01. contoso. com; San = Meet. contoso. com; San = Meet. fabrikam. com; San = dialin. contoso. com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN = SE01. contoso. com; San = webcon01. contoso. com; San = \* . contoso.com  <br/> |Wenn Sie über mehrere einfache URLs verfügen, müssen Sie Sie alle als Alternative Antragstellernamen einbeziehen.  <br/> Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.  <br/> |
   
Zertifikate für Front-End-Server in einer Enterprise Edition-Front-End-Pool:
  
|**Zertifikat**|**Antragstellername/Allgemeiner Name**|**Alternativer Antragstellername**|**Beispiel**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|Standard  <br/> |FQDN des Pools  <br/> |FQDN des Pools und FQDN des Servers  <br/> Wenn mehrere SIP-Domänen vorhanden sind und die automatische Clientkonfiguration aktiviert wurde, erkennt der Zertifikat-Assistent die unterstützten FQDNs für SIP-Domänen und fügt diese hinzu.  <br/> Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich (Domain Name System) festgelegt ist, benötigen Sie auch Einträge für "sip.sipDomäne" (für jede vorhandene SIP-Domäne).  <br/> |SN = EEpool. contoso. com; San = EEpool. contoso. com; San = ee01. contoso. com  <br/> Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch "SAN=sip.contoso.com; SAN=sip.fabrikam.com".  <br/> |Der Assistent erkennt alle SIP-Domänen, die Sie während der Installation angegeben haben, und fügt sie dem alternativen Antragstellernamen (SAN) automatisch hinzu.  <br/> Sie können dieses Zertifikat auch für die Server-zu-Server-Authentifizierung verwenden.  <br/> |
|Web, intern  <br/> |FQDN des Pools  <br/> |Jeder der folgenden:  <br/> • Interner FQDN des Webs (der nicht mit dem FQDN des Servers identisch ist)  <br/> • Server-FQDN  <br/> • FQDN des Skype for Business Pools  <br/> UND  <br/> • Einfache URLs erfüllen  <br/> • Einfache URL für Einwahl  <br/> • Einfache admin-URL  <br/> ODER  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |SN = ee01. contoso. com; San = ee01. contoso. com; San = Meet. contoso. com; San = Meet. fabrikam. com; San = dialin. contoso. com; San = admin. contoso. com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN = ee01. contoso. com; San = ee01. contoso. com; San = \* . contoso.com  <br/> |Wenn Sie über mehrere einfache URLs verfügen, müssen Sie Sie alle als Alternative Antragstellernamen einbeziehen.  <br/> Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.  <br/> |
|Web, extern  <br/> |FQDN des Pools  <br/> |Jeder der folgenden:  <br/> • Externer FQDN des Webs  <br/> UND  <br/> • Einfache URL für Einwahl  <br/> • Einfache admin-URL  <br/> ODER  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |SN = ee01. contoso. com; San = webcon01. contoso. com; San = Meet. contoso. com; San = Meet. fabrikam. com; San = dialin. contoso. com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN = ee01. contoso. com; San = webcon01. contoso. com; San = \* . contoso.com  <br/> |Wenn Sie über mehrere einfache URLs verfügen, müssen Sie Sie alle als Alternative Antragstellernamen einbeziehen.  <br/> Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.  <br/> |
   
Zertifikate für den Director:
  
|**Zertifikat**|**Antragstellername/Allgemeiner Name**|**Alternativer Antragstellername**|**Beispiel**|
|:-----|:-----|:-----|:-----|
|Standard  <br/> |Directorpool  <br/> |FQDN des Directors, FQDN des Directorpool.  <br/> Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien strikte DNS-Übereinstimmungen erforderlich sind, benötigen Sie auch Einträge für SIP. sipdomain "(für jede SIP-Domäne, die Sie haben).  <br/> |Pool.contoso.com; San = dir01. contoso. com  <br/> Wenn es sich bei diesem Director-Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch "SAN=sip.contoso.com; SAN=sip.fabrikam.com".  <br/> |
|Web, intern  <br/> |FQDN des Servers  <br/> |Jeder der folgenden:  <br/> • Interner FQDN des Webs (entspricht dem FQDN des Servers)  <br/> • Server-FQDN  <br/> • FQDN des Skype for Business Pools  <br/> UND  <br/> • Einfache URLs erfüllen  <br/> • Einfache URL für Einwahl  <br/> • Einfache admin-URL  <br/> ODER  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |SN = dir01. contoso. com; San = dir01. contoso. com; San = Meet. contoso. com; San = Meet. fabrikam. com; San = dialin. contoso. com; San = admin. contoso. com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN = dir01. contoso. com; San = dir01. contoso. com San = \* . contoso.com  <br/> |
|Web, extern  <br/> |FQDN des Servers  <br/> |Jeder der folgenden:  <br/> • Externer FQDN des Webs  <br/> UND  <br/> • Erfüllen einfacher URLs pro SIP-Domäne  <br/> • Einfache URL für Einwahl  <br/> ODER  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |Der externe Director-webfqdn muss sich von dem Front-End-Pool oder Front-End-Server unterscheiden.  <br/> SN = dir01. contoso. com; San = directorwebcon01. contoso. com San = Meet. contoso. com; San = Meet. fabrikam. com; San = dialin. contoso. com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN = dir01. contoso. com; San = directorwebcon01. contoso. com San = \* . contoso.com  <br/> |
   
Zertifikate für eigenständige Vermittlungsserver:
  
|**Zertifikat**|**Antragstellername/Allgemeiner Name**|**Alternativer Antragstellername**|**Beispiel**|
|:-----|:-----|:-----|:-----|
|Standard  <br/> |FQDN des Pools  <br/> |FQDN des Pools  <br/> FQDN des Pool Mitgliedsservers  <br/> |SN = medsvr-Pool.contoso.net; San = medsvr-Pool.contoso.net; San = medsvr01. contoso. net  <br/> |
   
Zertifikate für Survivable Branch Appliance:
  
|**Zertifikat**|**Antragstellername/Allgemeiner Name**|**Alternativer Antragstellername**|**Beispiel**|
|:-----|:-----|:-----|:-----|
|Standard  <br/> |FQDN der Appliance  <br/> |SIP.\<sipdomain\> (Sie benötigen nur einen Eintrag pro SIP-Domäne)  <br/> |SN = sba01. contoso. net; San = SIP. contoso. com; San = SIP. fabrikam. com  <br/> |
   
### <a name="certificates-for-your-persistent-chat-server"></a>Zertifikate für den Server für beständigen Chat

Wenn Sie den Server für beständigen Chat installieren, benötigen Sie ein Zertifikat, das von derselben Zertifizierungsstelle ausgestellt wird wie die, die von Ihren Skype for Business Server 2015 internen Servern verwendet wird. Dies muss für jeden Server ausgeführt werden, auf dem beständiger Chat Webdienste für das Hochladen/Herunterladen von Dateien erfolgt. Es wird dringend empfohlen, dass Sie über die erforderlichen Zertifikate verfügen, bevor Sie mit der Installation des beständigen Chats beginnen, und wenn Ihre Zertifizierungsstelle extern ist, umso mehr (diese Dinge können ein wenig Zeit in Anspruch nehmen, um ausgegeben zu werden).
  
### <a name="certificates-for-external-user-access-edge"></a>Zertifikate für den Zugriff durch externe Benutzer (Edge)

Skype for Business Server 2015 unterstützt die Verwendung eines **einzelnen öffentlichen Zertifikats** für Access-und Webkonferenz-Edge-externe Schnittstellen sowie den a/V-Authentifizierungsdienst, der über die Edgeserver bereitgestellt wird. In der internen Edge-Schnittstelle wird in der Regel ein privates Zertifikat verwendet, das von ihrer internen Zertifizierungsstelle ausgestellt wird, aber wenn Sie es bevorzugen, können Sie auch ein öffentliches Zertifikat verwenden, wenn es von einer vertrauenswürdigen Zertifizierungsstelle stammt.
  
Ihr Reverseproxy (Reverse Proxy) verwendet auch ein öffentliches Zertifikat und verschlüsselt die Kommunikation zwischen Ihrer RP und den Clients und die RP mit internen Servern mithilfe von http (genauer gesagt TLS über HTTP).
  
### <a name="certificates-for-mobility"></a>Zertifikate für Mobilität

Wenn Sie Mobilität bereitstellen und die automatische Ermittlung für mobile Clients unterstützen, müssen Sie einige zusätzliche Alternative Antragstellernamen-Einträge in Ihre Zertifikate aufnehmen, um die sicheren Verbindungen von den mobilen Clients zu unterstützen.
  
Welche certs? Sie benötigen San-Namen für die automatische Ermittlung der Zertifikate hier:
  
- Directorpool
    
- Front-End-Pool
    
- Reverseproxy
    
Wir werden die Einzelheiten in jeder Tabelle unten auflisten.
  
Nun ist hier eine kleine Vorplanung gut, aber manchmal haben Sie Skype for Business Server 2015 bereitgestellt, ohne dass Sie Mobilität bereitstellen möchten, und das kommt auf die Reihe, wenn Sie bereits über Zertifikate in Ihrer Umgebung verfügen. Die Neuausstellung über eine interne Zertifizierungsstelle ist normalerweise recht einfach, aber mit öffentlichen Zertifikaten einer öffentlichen Zertifizierungsstelle kann dies ein wenig teurer sein.
  
Wenn Sie sich das ansehen, und wenn Sie viele SIP-Domänen haben (wodurch das Hinzufügen von Sans teurer wäre), können Sie den Reverseproxy so konfigurieren, dass er http für die anfängliche AutoErmittlungsdienst Anforderung verwendet, anstatt HTTPS zu verwenden (Dies ist die Standardkonfiguration). Das Thema Planung für Mobilität enthält weitere Informationen dazu.
  
Zertifikatanforderungen für Directorpool und Front-End-Pool:
  
|**Beschreibung**|**San-Eintrag**|
|:-----|:-----|
|URL des internen AutoErmittlungsdiensts  <br/> |San = "lyncdiscoverinternal".\<sipdomain\>  <br/> |
|URL des externen AutoErmittlungsdiensts  <br/> |San = lyncdiscover.\<sipdomain\>  <br/> |
   
Alternativ können Sie auch "San =" verwenden \* .\<sipdomain\>
  
Zertifikatanforderungen für Reverse Proxys (öffentliche Zertifizierungsstellen):
  
|**Beschreibung**|**San-Eintrag**|
|:-----|:-----|
|URL des externen AutoErmittlungsdiensts  <br/> |San = lyncdiscover.\<sipdomain\>  <br/> |
   
Dieses San muss dem Zertifikat zugewiesen werden, das dem SSL-Listener auf dem Reverseproxy zugewiesen ist.
  
> [!NOTE]
> Der Listener des Reverseproxys wird Sans für Ihre externe Webdienste-URL (n) haben. Einige Beispiele wären San = skypewebextpool01. contoso. com und dirwebexternal.contoso.com, wenn Sie den Director bereitgestellt haben (optional). 
  
## <a name="file-share"></a>Dateifreigabe
<a name="Fileshare"> </a>

Skype for Business Server 2015 kann dieselbe Dateifreigabe für alle Dateispeicher verwenden. Sie müssen Folgendes berücksichtigen:
  
- Eine Dateifreigabe muss entweder im Direct-Attached Storage (das) oder im San (Storage Area Network) vorhanden sein, und dies umfasst das verteilte Datei System (DFS) sowie ein redundantes Array von unabhängigen Datenträgern (RAID) für Dateispeicher. Weitere Informationen zum DFS für Windows Server 2012 finden Sie auf [dieser DFS-Seite](https://technet.microsoft.com/library/jj127250.aspx).
    
- Es wird ein freigegebener Cluster für die Dateifreigabe empfohlen. Wenn Sie eine verwenden, sollten Sie Windows Server 2012 oder Windows Server 2012 R2 Cluster. Windows Server 2008 R2 ist ebenfalls akzeptabel. Warum die neuesten Fenster? Ältere Versionen verfügen möglicherweise nicht über die richtigen Berechtigungen, um alle Features zu aktivieren. Sie können die Cluster Verwaltung verwenden, um die Dateifreigaben zu erstellen, und diese Informationen werden Ihnen bei der [Erstellung von Dateifreigaben in einem Cluster](https://support.microsoft.com/help/224967/how-to-create-file-shares-on-a-cluster) Artikel helfen.
    
> [!CAUTION] 
> Sie sollten wissen, dass die Verwendung von NAS (Network Attached Storage) als Dateifreigabe nicht unterstützt wird, verwenden Sie daher eine der oben aufgeführten Optionen. 
  
