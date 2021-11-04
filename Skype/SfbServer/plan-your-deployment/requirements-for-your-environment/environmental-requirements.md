---
title: Umgebungsanforderungen für Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4812c444-2546-48d7-9ca7-b71fce508ed8
description: 'Zusammenfassung: Konfigurieren Sie Ihre Nicht-Serveranforderungen für Skype for Business Server 2015. Es gibt eine Vielzahl von Funktionen, die Sie vor der Bereitstellung konfigurieren möchten, einschließlich Active Directory, DNS, Zertifikaten und Dateifreigaben.'
ms.openlocfilehash: ab3192e7a9459f86ed61277db682a8b22f0725ec
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60749924"
---
# <a name="environmental-requirements-for-skype-for-business-server-2015"></a>Umgebungsanforderungen für Skype for Business Server 2015
 
**Zusammenfassung:** Konfigurieren Sie Ihre Nicht-Serveranforderungen für Skype for Business Server 2015. Es gibt eine Vielzahl von Funktionen, die Sie vor der Bereitstellung konfigurieren möchten, einschließlich Active Directory, DNS, Zertifikaten und Dateifreigaben.
  
Was ist eine Umgebungsanforderung für Skype for Business Server 2015? Nun, wir haben alles, was sich nicht direkt auf den Server bezieht, in dieses Thema eingefügt, sodass Sie nicht so viel herumklicken müssen. Wenn Sie nach Servervoraussetzungen suchen, können Sie sich die [Serveranforderungen für Skype for Business Server 2015-Dokument](server-requirements.md) ansehen. [Die Netzwerkplanung](../../plan-your-deployment/network-requirements/network-requirements.md) wird ebenfalls separat dokumentiert. Andernfalls haben wir dies in diesem Artikel:
  
- [Active Directory](environmental-requirements.md#AD)
  
- [Domain Name System (DNS)](environmental-requirements.md#DNS)
  
- [Zertifikate](environmental-requirements.md#Certs)
  
- [Dateifreigabe](environmental-requirements.md#Fileshare)
  
## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

Während viele Konfigurationsdaten für Server und Dienste im zentralen Verwaltungsspeicher von Skype for Business Server 2015 gespeichert sind, sind einige Dinge weiterhin in Active Directory gespeichert:
  
|**Active Directory-Objekte**|**Objekttypen**|
|:-----|:-----|
|Schemaerweiterungen  <br/> |Benutzerobjekterweiterungen  <br/> |
||Erweiterungen für Lync Server 2013 und Lync Server 2010, um die Abwärtskompatibilität mit den vorherigen unterstützten Versionen aufrechtzuerhalten.  <br/> |
|Daten  <br/> |Sip-URI des Benutzers und andere Benutzereinstellungen  <br/> |
||Kontaktobjekte für Anwendungen (z. B. die Reaktionsgruppenanwendung und die Konferenzzentralenanwendung).  <br/> |
||Aus Gründen der Abwärtskompatibilität veröffentlichte Daten.  <br/> |
||Ein Dienststeuerungspunkt (Service Control Point, SCP) für den zentralen Verwaltungsspeicher.  <br/> |
||Kerberos-Authentifizierungskonto (ein optionales Computerobjekt).  <br/> |
   
### <a name="os-for-domain-controllers"></a>Betriebssystem für Domänencontroller

Welches Domänencontroller-Betriebssystem kann also verwendet werden? Wir haben die folgende Liste:

- Windows Server 2019 (Sie müssen über Skype for Business Server kumulatives Update 5 oder höher 2015 verfügen)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
Die Domänenfunktionsebene jeder Domäne, in der Sie Skype for Business Server 2015 bereitstellen, und die Gesamtstrukturfunktionsebene jeder Gesamtstruktur, in der Sie Skype for Business Server 2015 bereitstellen, müssen eine der folgenden Sein:

- Windows Server 2019 (Sie müssen über Skype for Business Server kumulatives Update 5 oder höher 2015 verfügen)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
- Windows Server 2003
    
Können Sie in diesen Umgebungen schreibgeschützte Domänencontroller verwenden? Sicher, solange auch beschreibbare Domänencontroller am selben Standort wie der Skype for Business Server verfügbar sind.
  
Jetzt ist es wichtig zu wissen, dass Skype for Business Server 2015 keine Domänen mit nur einer Bezeichnung unterstützt. Welche sind das? Wenn Sie eine Stammdomäne mit der Bezeichnung "contoso.local" haben, ist dies in Ordnung. Wenn Sie über eine Stammdomäne verfügen, die nur als lokal bezeichnet wird, funktioniert dies nicht und wird daher nicht unterstützt. Etwas mehr dazu wurde [in diesem Knowledge Base-Artikel](https://support.microsoft.com/kb/300684/en-us)geschrieben.
  
Skype for Business Server 2015 unterstützt auch das Umbenennen von Domänen nicht. Wenn Sie dies wirklich tun müssen, müssen Sie Skype for Business Server 2015 deinstallieren, die Domäne umbenennen und dann Skype for Business Server 2015 neu installieren.
  
Schließlich können Sie es mit einer Domäne mit einer gesperrten AD DS-Umgebung zu tun haben, und das ist alles richtig. Weitere Informationen zum Bereitstellen von Skype for Business Server 2015 in dieser Art von Umgebung finden Sie in den Bereitstellungsdokumenten.
  
### <a name="ad-topologies"></a>AD-Topologien

Skype for Business Server 2015 unterstützten Topologien sind:
  
- Einzelne Gesamtstruktur mit einzelner Domäne
    
- Einzelne Gesamtstruktur mit einer Struktur und mehreren Domänen
    
- Einzelne Gesamtstruktur mit mehreren Strukturen und nicht zusammenhängenden Namespaces
    
- Mehrere Gesamtstrukturen in einer Topologie mit zentraler Gesamtstruktur
    
- Mehrere Gesamtstrukturen in einer Topologie mit Ressourcengesamtstruktur
    
- Mehrere Gesamtstrukturen in einer Skype for Business Ressourcengesamtstrukturtopologie mit Exchange Online
    
- Mehrere Gesamtstrukturen in einer Ressourcengesamtstrukturtopologie mit Skype for Business Online und Azure Active Directory Verbinden
    
Es gibt Diagramme und Beschreibungen, mit denen Sie ermitteln können, welche Topologie Sie in Ihrer Umgebung haben oder was Sie vor der Installation von Skype for Business Server 2015 einrichten müssen. Um dies einfach zu halten, schließen wir auch einen Schlüssel ein:
  
![Dies ist ein Schlüssel für die Symbole, die für Skype for Business Topologiediagramme verwendet werden.](../../media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>Einzelne Gesamtstruktur mit einzelner Domäne

![Diagramm der Active Directory-Gesamtstruktur mit einer einzelnen Domäne.](../../media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
Es wird nicht einfacher als dies, es ist eine einzelne Domänengesamtstruktur, dies ist eine allgemeine Topologie.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>Einzelne Gesamtstruktur mit einer Struktur und mehreren Domänen

![Eine einzelne Gesamtstruktur, eine einzelne Struktur und ein Stummschaltungsdomänendiagramm.](../../media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
Dieses Diagramm zeigt erneut eine einzelne Gesamtstruktur, hat aber auch eine oder mehrere untergeordnete Domänen (in diesem spezifischen Beispiel gibt es drei). Die Domäne, in der die Benutzer erstellt werden, unterscheidet sich möglicherweise von der Domäne, in der 2015 bereitgestellt wird Skype for Business Server. Warum machen Sie sich Gedanken darüber? Es ist wichtig zu beachten, dass bei der Bereitstellung eines Skype for Business Server Front-End-Pools alle Server in diesem Pool in einer einzigen Domäne sein müssen. Sie können domänenübergreifende Verwaltung über Skype for Business Server unterstützung von Windows universellen Administratorgruppen haben.
  
Zurück zum obigen Diagramm können Sie sehen, dass Benutzer aus einer Domäne auf Skype for Business Server Pools aus derselben Domäne oder aus verschiedenen Domänen zugreifen können, auch wenn sich diese Benutzer in einer untergeordneten Domäne befinden.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>Einzelne Gesamtstruktur mit mehreren Strukturen und nicht zusammenhängenden Namespaces

![Eine einzelne Gesamtstruktur, mehrere Strukturen und ein nicht zusammenhängendes Namespacediagramm.](../../media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
Möglicherweise haben Sie eine Topologie ähnlich wie in diesem Diagramm, in der Sie über eine Gesamtstruktur verfügen, aber innerhalb dieser Gesamtstruktur sind mehrere Domänen mit separaten AD-Namespaces vorhanden. Wenn dies der Fall ist, ist dieses Diagramm eine gute Abbildung, da wir Benutzer in drei verschiedenen Domänen haben, die auf Skype for Business Server 2015 zugreifen. Durchgezogene Linien deuten darauf hin, dass sie auf einen Skype for Business Server Pool in ihrer eigenen Domäne zugreifen, während eine gestrichelte Linie angibt, dass sie zu einem Pool in einer anderen Struktur wechseln.
  
Wie Sie sehen können, können Benutzer in derselben Domäne, derselben Struktur oder sogar einer anderen Struktur erfolgreich auf Pools zugreifen.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>Mehrere Gesamtstrukturen in einer Topologie mit zentraler Gesamtstruktur

![Mehrere Gesamtstrukturen in einem Topologiediagramm der zentralen Gesamtstruktur.](../../media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype for Business Server 2015 unterstützt mehrere Gesamtstrukturen, die in einer Topologie mit zentraler Gesamtstruktur konfiguriert sind. Wenn Sie nicht sicher sind, was Sie haben, verwendet die zentrale Gesamtstruktur in der Topologie Objekte darin, um Benutzer in den anderen Gesamtstrukturen darzustellen, und hostet Benutzerkonten für alle Benutzer in der Gesamtstruktur.
  
Wie funktioniert dies? Nun, ein Verzeichnissynchronisierungsprodukt (z. B. Forefront Identity Manager oder FIM) verwaltet die Benutzerkonten Ihrer Organisation während ihres bestehens. Wenn ein Konto erstellt oder aus einer Gesamtstruktur gelöscht wird, wird diese Änderung mit dem entsprechenden Kontakt in der zentralen Gesamtstruktur synchronisiert.
  
Wenn Ihre AD-Infrastruktur direkt auf diese Topologie umstellen kann, ist dies möglicherweise nicht einfach, aber wenn Sie bereits dort sind oder ihre Gesamtstrukturinfrastruktur planen, kann dies eine gute Wahl sein. Sie können ihre Skype for Business Server 2015-Bereitstellung in einer einzigen Gesamtstruktur zentralisieren, während Benutzer das Vorhandensein anderer Benutzer in einer beliebigen Gesamtstruktur suchen, kommunizieren und anzeigen können. Alle Benutzerkontaktupdates werden automatisch mit Synchronisierungssoftware behandelt.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Mehrere Gesamtstrukturen in einer Skype for Business Ressourcengesamtstrukturtopologie
<a name="BKMK_multipleforestopology"> </a>

![Mehrere Gesamtstrukturen in einem Topologiediagramm der Ressourcengesamtstruktur.](../../media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
Eine Topologie der Ressourcengesamtstruktur wird ebenfalls unterstützt. Hier ist eine Gesamtstruktur für die Ausführung Ihrer Serveranwendungen vorgesehen, z. B. Microsoft Exchange Server und Skype for Business Server 2015. Diese Ressourcengesamtstrukturen hosten auch eine synchronisierte Darstellung aktiver Benutzerobjekte, jedoch keine angemeldeten Benutzerkonten. Die Ressourcengesamtstruktur ist also eine freigegebene Dienstumgebung für andere Gesamtstrukturen, in denen sich Benutzerobjekte befinden, und sie haben eine Vertrauensstellung auf Gesamtstrukturebene mit der Ressourcengesamtstruktur.
  
Beachten Sie, dass Exchange Server in derselben Ressourcengesamtstruktur wie Skype for Business Server oder in einer anderen Gesamtstruktur bereitgestellt werden können.
  
Um Skype for Business Server 2015 in dieser Art von Topologie bereitzustellen, erstellen Sie ein deaktiviertes Benutzerobjekt in der Ressourcengesamtstruktur für jedes Benutzerkonto in den Benutzergesamtstrukturen (wenn sich Microsoft Exchange Server bereits in der Umgebung befindet, ist dies möglicherweise für Sie der Fall). Anschließend benötigen Sie ein Verzeichnissynchronisierungstool (z. B. Forefront Identity Manager oder FIM), um Benutzerkonten während ihres Lebenszyklus zu verwalten.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Mehrere Gesamtstrukturen in einer Skype for Business Ressourcengesamtstrukturtopologie mit Exchange Online
<a name="BKMK_multipleforestopology"> </a>

Diese Topologie ähnelt der Topologie, die in [mehreren Gesamtstrukturen in einer Skype for Business Topologie der Ressourcengesamtstruktur](environmental-requirements.md#BKMK_multipleforestopology)beschrieben ist.
  
In dieser Topologie gibt es eine oder mehrere Benutzergesamtstrukturen, und Skype for Business Server in einer dedizierten Ressourcengesamtstruktur bereitgestellt wird. Exchange Server können lokal in derselben Ressourcengesamtstruktur oder einer anderen Gesamtstruktur bereitgestellt und für Hybridbereitstellungen mit Exchange Online konfiguriert werden, oder E-Mail-Dienste können ausschließlich durch Exchange Online für die lokalen Konten bereitgestellt werden. Für diese Topologie ist kein Diagramm verfügbar.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Mehrere Gesamtstrukturen in einer Ressourcengesamtstrukturtopologie mit Skype for Business Online und Azure Active Directory Verbinden
<a name="BKMK_multipleforestopology"> </a>

![Zeigt zwei AD-Gesamtstrukturen, eine Benutzergesamtstruktur und eine Ressourcengesamtstruktur an. Die beiden Gesamtstrukturen haben eine Vertrauensstellung. Sie werden mit Microsoft 365 oder Office 365 mit Azure AD Verbinden synchronisiert. Alle Benutzer sind über Microsoft 365 oder Office 365 für Skype for Business aktiviert.](../../media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
In diesem Szenario gibt es mehrere lokale Gesamtstrukturen mit einer Ressourcengesamtstrukturtopologie. Es besteht eine voll vertrauenswürdige Beziehung zwischen den Active Directory-Gesamtstrukturen. Das Azure Active Directory Verbinden Tool wird verwendet, um Konten zwischen den lokalen Benutzergesamtstrukturen und Microsoft 365 oder Office 365 zu synchronisieren.
  
 Die Organisation verfügt auch über Microsoft 365 oder Office 365 und verwendet [Azure Active Directory Verbinden,](/previous-versions/azure/azure-services/dn832695(v=azure.100)) um ihre lokalen Konten mit Microsoft 365 oder Office 365 zu synchronisieren. Benutzer, die für Skype for Business aktiviert sind, werden über Microsoft 365 oder Office 365 und Skype for Business Online aktiviert. Skype for Business Server wird nicht lokal bereitgestellt.
  
Die Single Sign-On-Authentifizierung wird von einer Active Directory-Verbunddienste-Farm in der Benutzergesamtstruktur bereitgestellt.
  
In diesem Szenario wird die Bereitstellung Exchange lokalen, Exchange Online, einer hybriden Exchange-Lösung oder die Bereitstellung Exchange unterstützt. (Das Diagramm zeigt nur Exchange lokalen, aber die anderen Exchange Lösungen werden ebenfalls vollständig unterstützt.)
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>Mehrere Gesamtstrukturen in einer Ressourcengesamtstrukturtopologie mit hybrider Skype for Business
<a name="BKMK_multipleforestopology"> </a>

In diesem Szenario gibt es eine oder mehrere lokale Benutzergesamtstrukturen, und Skype for Business in einer dedizierten Ressourcengesamtstruktur bereitgestellt und für den Hybridmodus mit Skype for Business Online konfiguriert ist. Exchange Server können lokal in derselben Ressourcengesamtstruktur oder in einer anderen Gesamtstruktur bereitgestellt und für hybride Exchange Online konfiguriert werden. Alternativ können E-Mail-Dienste ausschließlich von Exchange Online für die lokalen Konten bereitgestellt werden.
  
Weitere Informationen finden Sie unter Konfigurieren einer Umgebung mit [mehreren Gesamtstrukturen für hybride Skype for Business.](../../../SfbHybrid/hybrid/configure-a-multi-forest-environment-for-hybrid.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)
  
## <a name="domain-name-system-dns"></a>Domain Name System (DNS)
<a name="DNS"> </a>

Skype for Business Server 2015 erfordert DNS aus den folgenden Gründen:
  
- DNS ermöglicht Skype for Business Server 2015, interne Server oder Pools zu ermitteln, sodass die Kommunikation zwischen Servern möglich ist.
    
- DNS ermöglicht Clientcomputern das Ermitteln des Front-End-Pools oder Standard Edition Servers, der für SIP-Transaktionen verwendet wird.
    
- Einfache URLs für Konferenzen werden den Servern zugeordnet, auf denen diese Konferenzen gehostet werden.
    
- DNS ermöglicht externen Benutzern und Clientcomputern die Verbindung mit Ihren Edgeservern oder dem HTTP-Reverseproxy für Chatnachrichten oder Konferenzen.
    
- UC-Geräte (Unified Communications), die nicht angemeldet sind, können den Front-End-Pool oder Standard Edition Server ermitteln, auf dem der Geräteaktualisierungswebdienst ausgeführt wird, um Updates abzurufen und Protokolle zu senden.
    
- Mithilfe von DNS können mobile Clients Webdienstressourcen automatisch ermitteln, ohne dass Benutzer manuell URLs in ihre Geräteeinstellungen eingeben müssen.
    
- Und es wird beim DNS-Lastenausgleich verwendet.
    
Es ist wichtig zu beachten, dass Skype for Business Server 2015 keine internationalisierten Domänennamen (IDNs) unterstützt.
  
Und es ist äußerst wichtig zu beachten, dass jeder Name in DNS mit dem Computernamen identisch ist, der auf jedem Server konfiguriert ist, der von Skype for Business Server 2015 verwendet wird. Insbesondere können in der Umgebung keine Kurznamen vorhanden sein, und es müssen FQDNs für den Topologie-Generator vorhanden sein.
  
Dies scheint für jeden Computer logisch zu sein, der bereits einer Domäne beigetreten ist, aber wenn Sie über einen Edgeserver verfügen, der nicht mit Ihrer Domäne verbunden ist, hat er möglicherweise einen Kurznamen ohne Domänensuffix. Stellen Sie sicher, dass dies nicht der Fall ist, entweder im DNS oder auf dem Edgeserver oder einem Skype for Business Server 2015-Server oder -Pool.
  
Und verwenden Sie auf jeden Fall keine Unicode-Zeichen oder Unterstriche. Standardzeichen (A-Z, a-z, 0-9 und Bindestriche) sind die Zeichen, die von externem DNS und öffentlichen Zertifizierungsstellen unterstützt werden (Sie müssen dem SN im Zertifikat FQDNs zuweisen, vergessen Sie nicht), daher sparen Sie sich eine Menge Mühe, wenn Sie den Namen in diesem Sinne verwenden.
  
Weitere Informationen zu DNS-Anforderungen für Netzwerke finden Sie im Abschnitt ["Networking"](../../plan-your-deployment/network-requirements/network-requirements.md) in unserer Planungsdokumentation.
  
## <a name="certificates"></a>Zertifikate
<a name="Certs"> </a>

Eines der wichtigsten Dinge, die Sie vor der Bereitstellung tun können, ist sicherzustellen, dass Ihre Zertifikate in ordnung sind. Skype for Business Server 2015 benötigt eine Public Key-Infrastruktur (PKI) für TLS-Verbindungen (Transport Layer Security) und MTLS-Verbindungen (Mutual Transport Layer Security). Um auf standardisierte Weise sicher zu kommunizieren, verwendet Skype for Business Server Zertifikate, die von Zertifizierungsstellen (Certificate Authorities, CAs) ausgestellt wurden.
  
Dies sind einige der Dinge, für die Skype for Business Server 2015 Zertifikate verwendet:
  
- TLS-Verbindungen zwischen Clients und Servern
    
- MTLS-Verbindungen zwischen Servern
    
- Partnerverbund mit automatischer DNS-Ermittlung von Partnern
    
- Zugriff von Remotebenutzern auf Sofortnachrichten
    
- Externer Benutzerzugriff auf Audio-/Videositzungen ,Anwendungsfreigabe und Konferenzen
    
- Kommunizieren mit Webanwendungen und Outlook Web Access (OWA)
    
Die Zertifikatplanung ist daher ein Muss. Sehen wir uns nun eine Liste einiger Dinge an, die Sie beim Anfordern von Zertifikaten beachten müssen:
  
- Alle Serverzertifikate müssen die Serverautorisierung (Enhanced Key Usage [EKU], erweiterte Schlüsselverwendung für Server) unterstützen.
    
- Alle Serverzertifikate müssen einen Zertifikatsperrlisten-Verteilungspunkt unterstützen.
    
- Alle Zertifikate müssen mithilfe eines Signaturalgorithmus signiert werden, der vom Betriebssystem unterstützt wird. Skype for Business Server 2015 unterstützt die SUITE SHA-1 und SHA-2 der Digestgrößen (224, 256, 384 und 512 Bit) und erfüllt oder überschreitet die Betriebssystemanforderungen.
    
- Die automatische Registrierung wird für interne Server unterstützt, die Skype for Business Server 2015 ausgeführt werden.
    
- Die automatische Registrierung wird für Skype for Business Server 2015-Edgeserver nicht unterstützt.
    
- Wenn Sie eine webbasierte Zertifikatanforderung an eine Windows Server 2003-Zertifizierungsstelle senden möchten, muss diese von einem Computer aus gesendet werden, auf dem entweder Windows Server 2003 mit SP2 oder Windows XP ausgeführt wird.
    
> [!NOTE]
> Obwohl KB922706 Unterstützung für das Beheben von Problemen bei der Registrierung von Webzertifikaten bei einer Windows Server 2003-Zertifikatdienste-Webregistrierung bietet, ist es nicht möglich, Windows Server 2008, Windows Vista oder Windows 7 zu verwenden, um ein Zertifikat von einer Windows Server 2003-Zertifizierungsstelle anzufordern. 
  
> [!NOTE]
> Die Verwendung des RSASSA-PSS-Signaturalgorithmus wird nicht unterstützt und kann unter anderem zu Fehlern bei Anmelde- und Anrufweiterleitungsproblemen führen. 

> [!NOTE]
> Skype for Business Server 2015 unterstützt keine CNG-Zertifikate.
  
- Verschlüsselungsschlüssellängen von 1024, 2048 und 4096 werden unterstützt. Es werden Schlüssellängen von 2048 und höher empfohlen.
    
- Der Standardmäßige Digestalgorithmus oder Hashsignaturalgorithmus ist RSA. Die Algorithmen ECDH_P256, ECDH_P384 und ECDH_P521 werden ebenfalls unterstützt.
    
Das ist also eine Menge zu bedenken, und auf jeden Fall gibt es eine Vielzahl von Komfortstufen beim Anfordern von Zertifikaten von einer Zertifizierungsstelle. Nachfolgend finden Sie weitere Anleitungen, um Ihre Planung so problemlos wie möglich zu gestalten.
  
### <a name="certificates-for-your-internal-servers"></a>Zertifikate für Ihre internen Server

Sie benötigen Zertifikate für die meisten ihrer internen Server, und höchstwahrscheinlich erhalten Sie diese von einer internen Zertifizierungsstelle (die sich in Ihrer Domäne befindet). Wenn Sie möchten, können Sie diese Zertifikate von einer externen Zertifizierungsstelle (eine im Internet) anfordern. Wenn Sie sich fragen, zu welcher öffentlichen Zertifizierungsstelle Sie gehen sollten, können Sie sich die Liste der [Unified Communications-Zertifikatpartner](../../../SfbPartnerCertification/certification/services-ssl.md) ansehen.
  
Außerdem benötigen Sie Zertifikate, wenn Skype for Business Server 2015 mit anderen Anwendungen und Servern kommuniziert, z. B. Microsoft Exchange Server. Dies muss natürlich ein Zertifikat sein, das von anderen Apps und Servern unterstützt werden kann. Skype for Business Server 2015 und andere Microsoft-Produkte unterstützen das Open Authorization (OAuth)-Protokoll für die Server-zu-Server-Authentifizierung und -Autorisierung. Wenn Sie daran interessiert sind, haben wir einen zusätzlichen Planungsartikel für OAuth und Skype for Business Server 2015.
  
Skype for Business Server 2015 umfasst auch Unterstützung für (ohne Dass) Zertifikate, die mit der sha-256-Kryptohashfunktion signiert wurden. Um den externen Zugriff mit SHA-256 zu unterstützen, muss das externe Zertifikat von einer öffentlichen Zertifizierungsstelle mit SHA-256 ausgestellt werden.
  
Um die Dinge einfach zu halten, haben wir die Zertifikatanforderungen für Standard Edition Server, Front-End-Pools und andere Rollen in die folgenden Tabellen eingefügt, wobei die fiktiven contoso.com für Beispiele verwendet werden (Sie werden wahrscheinlich etwas anderes für Ihre Umgebung verwenden). Hierbei handelt es sich um standardmäßige Webserverzertifikate mit privaten Schlüsseln, die nicht exportierbar sind. Einige zusätzliche Punkte, die Sie beachten müssen:
  
- Die erweiterte Schlüsselverwendung (EKU) des Servers wird automatisch konfiguriert, wenn Sie den Zertifikat-Assistenten zum Anfordern von Zertifikaten verwenden.
    
- Jeder Anzeigename des Zertifikats muss im Computerspeicher eindeutig sein.
    
- Gemäß den folgenden Beispielnamen müssen sie dem alternativen Antragstellernamen (Subject Alternative Name, SAN) des Zertifikats hinzugefügt werden, wenn Sie sipinternal.contoso.com oder sipexternal.contoso.com in Ihrem DNS konfiguriert haben.
    
Zertifikate für Standard Edition Server:
  
|**Zertifikat**|**Antragstellername/allgemeiner Name**|**Alternativer Antragstellername**|**Beispiel**|**Kommentare**|
|:-----|:-----|:-----|:-----|:-----|
|Standard  <br/> |FQDN des Pools  <br/> |FQDN des Pools und FQDN des Servers  <br/> Wenn mehrere SIP-Domänen vorhanden sind und die automatische Clientkonfiguration aktiviert wurde, erkennt der Zertifikat-Assistent die unterstützten FQDNs für SIP-Domänen und fügt diese hinzu.  <br/> Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich (Domain Name System) festgelegt ist, benötigen Sie auch Einträge für "sip.sipDomäne" (für jede vorhandene SIP-Domäne).  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com  <br/> Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch "SAN=sip.contoso.com; SAN=sip.fabrikam.com".  <br/> |Auf einem Standard Edition-Server entspricht der Server-FQDN dem Pool-FQDN.  <br/> Der Assistent erkennt alle SIP-Domänen, die Sie während des Setups angegeben haben, und fügt sie automatisch als alternative Antragstellernamen hinzu.  <br/> Sie können dieses Zertifikat auch für die Server-zu-Server-Authentifizierung verwenden.  <br/> |
|Web, intern  <br/> |FQDN des Servers  <br/> |Jeder der folgenden:  <br/> • Interner Web-FQDN (identisch mit dem FQDN des Servers)  <br/> AND  <br/> • Erfüllen einfacher URLs  <br/> • Einfache EINWAHL-URL  <br/> • Einfache ADMIN-URL  <br/> OR  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN=se01.contoso.com; SAN=se01.contoso.com; SAN= \* .contoso.com  <br/> |Sie können den internen Web-FQDN im Topologie-Generator nicht überschreiben.  <br/> Wenn Sie über mehrere einfache Besprechungs-URLs verfügen, müssen Sie alle als SANs einschließen.  <br/> Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.  <br/> |
|Web, extern  <br/> |FQDN des Servers  <br/> |Jeder der folgenden:  <br/> • Externer Web-FQDN  <br/> AND  <br/> • Einfache EINWAHL-URL  <br/> • Besprechung einfacher URLs pro SIP-Domäne  <br/> OR  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN= \* .contoso.com  <br/> |Wenn Sie über mehrere einfache Besprechungs-URLs verfügen, müssen Sie alle als alternative Antragstellernamen angeben.  <br/> Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.  <br/> |
   
Zertifikate für Front-End-Server in einem Enterprise Edition Front-End-Pool:
  
|**Zertifikat**|**Antragstellername/allgemeiner Name**|**Alternativer Antragstellername**|**Beispiel**|**Kommentare**|
|:-----|:-----|:-----|:-----|:-----|
|Standard  <br/> |FQDN des Pools  <br/> |FQDN des Pools und FQDN des Servers  <br/> Wenn mehrere SIP-Domänen vorhanden sind und die automatische Clientkonfiguration aktiviert wurde, erkennt der Zertifikat-Assistent die unterstützten FQDNs für SIP-Domänen und fügt diese hinzu.  <br/> Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich (Domain Name System) festgelegt ist, benötigen Sie auch Einträge für "sip.sipDomäne" (für jede vorhandene SIP-Domäne).  <br/> |SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com  <br/> Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch "SAN=sip.contoso.com; SAN=sip.fabrikam.com".  <br/> |Der Assistent erkennt alle SIP-Domänen, die Sie während der Installation angegeben haben, und fügt sie dem alternativen Antragstellernamen (SAN) automatisch hinzu.  <br/> Sie können dieses Zertifikat auch für die Server-zu-Server-Authentifizierung verwenden.  <br/> |
|Web, intern  <br/> |FQDN des Pools  <br/> |Jeder der folgenden:  <br/> • Interner Web-FQDN (der NICHT mit dem FQDN des Servers identisch ist)  <br/> • Server-FQDN  <br/> • Skype for Business Pool-FQDN  <br/> AND  <br/> • Erfüllen einfacher URLs  <br/> • Einfache EINWAHL-URL  <br/> • Einfache ADMIN-URL  <br/> OR  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN= \* .contoso.com  <br/> |Wenn Sie über mehrere einfache Besprechungs-URLs verfügen, müssen Sie alle als alternative Antragstellernamen angeben.  <br/> Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.  <br/> |
|Web, extern  <br/> |FQDN des Pools  <br/> |Jeder der folgenden:  <br/> • Externer Web-FQDN  <br/> AND  <br/> • Einfache EINWAHL-URL  <br/> • Einfache ADMIN-URL  <br/> OR  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN= \* .contoso.com  <br/> |Wenn Sie über mehrere einfache Besprechungs-URLs verfügen, müssen Sie alle als alternative Antragstellernamen angeben.  <br/> Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.  <br/> |
   
Zertifikate für den Director:
  
|**Zertifikat**|**Antragstellername/allgemeiner Name**|**Alternativer Antragstellername**|**Beispiel**|
|:-----|:-----|:-----|:-----|
|Standard  <br/> |Directorpool  <br/> |FQDN des Director, FQDN des Directorpools.  <br/> Wenn dieser Pool der Server für die automatische Anmeldung für Clients ist und in der Gruppenrichtlinie ein strenger DNS-Abgleich erforderlich ist, benötigen Sie auch Einträge für sip.sipdomain (für jede SIP-Domäne, die Sie haben).  <br/> |pool.contoso.com; SAN=dir01.contoso.com  <br/> Wenn es sich bei diesem Director-Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch "SAN=sip.contoso.com; SAN=sip.fabrikam.com".  <br/> |
|Web, intern  <br/> |FQDN des Servers  <br/> |Jeder der folgenden:  <br/> • Interner Web-FQDN (identisch mit dem FQDN des Servers)  <br/> • Server-FQDN  <br/> • Skype for Business Pool-FQDN  <br/> AND  <br/> • Erfüllen einfacher URLs  <br/> • Einfache EINWAHL-URL  <br/> • Einfache ADMIN-URL  <br/> OR  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN=dir01.contoso.com; SAN=dir01.contoso.com SAN= \* .contoso.com  <br/> |
|Web, extern  <br/> |FQDN des Servers  <br/> |Jeder der folgenden:  <br/> • Externer Web-FQDN  <br/> AND  <br/> • Besprechung einfacher URLs pro SIP-Domäne  <br/> • Einfache EINWAHL-URL  <br/> OR  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |Der externe Web-FQDN des Director muss sich vom Front-End-Pool oder Front-End-Server unterscheiden.  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN= \* .contoso.com  <br/> |
   
Zertifikate für eigenständigen Vermittlungsserver:
  
|**Zertifikat**|**Antragstellername/allgemeiner Name**|**Alternativer Antragstellername**|**Beispiel**|
|:-----|:-----|:-----|:-----|
|Standard  <br/> |FQDN des Pools  <br/> |FQDN des Pools  <br/> FQDN des Poolmitgliedsservers  <br/> |SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net  <br/> |
   
Zertifikate für Survivable Branch Appliance:
  
|**Zertifikat**|**Antragstellername/allgemeiner Name**|**Alternativer Antragstellername**|**Beispiel**|
|:-----|:-----|:-----|:-----|
|Standard  <br/> |FQDN der Appliance  <br/> |SIP.\<sipdomain\> (Sie benötigen nur einen Eintrag pro SIP-Domäne)  <br/> |SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-your-persistent-chat-server"></a>Zertifikate für Ihren Server für beständigen Chat

Bei der Installation des Servers für beständigen Chat benötigen Sie ein Zertifikat, das von derselben Zertifizierungsstelle ausgestellt wurde wie das von Ihren internen Servern Skype for Business Server 2015. Dies muss für jeden Server ausgeführt werden, auf dem Webdienste für beständigen Chat für Datei Hochladen/Herunterladen ausgeführt werden. Es wird dringend empfohlen, dass Sie über die erforderlichen Zertifikate verfügen, bevor Sie mit der Installation des beständigen Chats beginnen, und wenn Es sich bei Ihrer Zertifizierungsstelle um externe Zertifikate handelt (dies kann etwas Zeit in Anspruch nehmen, bis sie ausgestellt wurde).
  
### <a name="certificates-for-external-user-access-edge"></a>Zertifikate für externen Benutzerzugriff (Edge)

Skype for Business Server 2015 unterstützt die Verwendung eines **einzelnen öffentlichen Zertifikats** für externe Zugriffs- und Webkonferenz-Edgeschnittstellen sowie den A/V-Authentifizierungsdienst, der alle über die Edgeserver bereitgestellt wird. Ihre interne Edgeschnittstelle verwendet in der Regel ein privates Zertifikat, das von Ihrer internen Zertifizierungsstelle ausgestellt wurde. Wenn Sie dies bevorzugen, können Sie auch hierfür ein öffentliches Zertifikat verwenden, wenn es von einer vertrauenswürdigen Zertifizierungsstelle stammt.
  
Ihr Reverseproxy (RP) verwendet auch ein öffentliches Zertifikat und verschlüsselt die Kommunikation von Ihrem RP an Clients und das RP zu internen Servern mithilfe von HTTP (oder genauer gesagt TLS über HTTP).
  
### <a name="certificates-for-mobility"></a>Zertifikate für Mobilität

Wenn Sie Mobilität bereitstellen und die automatische Ermittlung für mobile Clients unterstützen, müssen Sie einige zusätzliche Einträge mit alternativen Antragstellernamen in Ihre Zertifikate aufnehmen, um die sicheren Verbindungen von den mobilen Clients zu unterstützen.
  
Welche Zertifikate? Hier benötigen Sie SAN-Namen für die automatische Erkennung der Zertifikate:
  
- Directorpool
    
- Front-End-Pool
    
- Reverse-Proxy
    
Wir werden die Einzelheiten in jeder tabelle unten auflisten.
  
Jetzt ist hier eine kleine Vorplanung gut, aber manchmal haben Sie Skype for Business Server 2015 bereitgestellt, ohne Mobilität bereitzustellen. Dies kommt ganz oben auf sich, wenn Sie bereits Zertifikate in Ihrer Umgebung haben. Die erneute Bereitstellung über eine interne Zertifizierungsstelle ist in der Regel ziemlich einfach, aber mit öffentlichen Zertifikaten von einer öffentlichen Zertifizierungsstelle kann dies etwas teurer sein.
  
Wenn Sie sich dies ansehen und viele SIP-Domänen haben (was das Hinzufügen von SANS verteuern würde), können Sie Ihren Reverseproxy so konfigurieren, dass er HTTP für die ursprüngliche AutoErmittlungsdienstanforderung verwendet, anstatt HTTPS (die Standardkonfiguration) zu verwenden. Weitere Informationen hierzu finden Sie im Thema "Planung für Mobilität".
  
Zertifikatanforderungen für Directorpool und Front-End-Pool:
  
|**Beschreibung**|**SAN-Eintrag**|
|:-----|:-----|
|Url des internen AutoErmittlungsdiensts  <br/> |SAN=lyncdiscoverinternal.\<sipdomain\>  <br/> |
|URL des externen AutoErmittlungsdiensts  <br/> |SAN=lyncdiscover.\<sipdomain\>  <br/> |
   
Alternativ können Sie SAN= \* verwenden.\<sipdomain\>
  
Zertifikatanforderungen für Reverseproxys (öffentliche Zertifizierungsstelle):
  
|**Beschreibung**|**SAN-Eintrag**|
|:-----|:-----|
|URL des externen AutoErmittlungsdiensts  <br/> |SAN=lyncdiscover.\<sipdomain\>  <br/> |
   
Dieser SAN muss dem Zertifikat zugewiesen werden, das dem SSL-Listener auf Ihrem Reverseproxy zugewiesen ist.
  
> [!NOTE]
> Der Reverseproxylistener verfügt über SANs für ihre externen Webdienst-URLs. Beispiele hierfür sind SAN=skypewebextpool01.contoso.com und dirwebexternal.contoso.com, wenn Sie den Director bereitgestellt haben (optional). 
  
## <a name="file-share"></a>Dateifreigabe
<a name="Fileshare"> </a>

Skype for Business Server 2015 kann dieselbe Dateifreigabe für den gesamten Dateispeicher verwenden. Beachten Sie Dabei Folgendes:
  
- Eine Dateifreigabe muss sich entweder auf direct Attached Storage (DAS) oder einem Speicherbereichsnetzwerk (SAN) befinden. Dazu gehören das dfs (Distributed File System) und ein redundantes Array unabhängiger Datenträger (RAID) für Dateispeicher. Weitere Informationen zu DFS für Windows Server 2012 finden Sie auf [dieser DFS-Seite.](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj127250(v=ws.11))
    
- Wir empfehlen einen freigegebenen Cluster für die Dateifreigabe. Wenn Sie eine verwenden, sollten Sie Windows Server 2012 oder Windows Server 2012 R2 clustern. Windows Server 2008 R2 ist auch akzeptabel. Warum die neuesten Windows? Ältere Versionen verfügen möglicherweise nicht über die richtigen Berechtigungen, um alle Features zu aktivieren. Sie können den Clusteradministrator zum Erstellen der Dateifreigaben verwenden. Dieser Artikel zum Erstellen von [Dateifreigaben in einem Clusterartikel](https://support.microsoft.com/help/224967/how-to-create-file-shares-on-a-cluster) hilft Ihnen bei diesen Details.
    
> [!CAUTION] 
> You should know that using network attached storage (NAS) as a file share isn't supported, so use one of the options listed above. 
