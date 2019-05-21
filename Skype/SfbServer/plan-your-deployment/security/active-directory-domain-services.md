---
title: Active Directory-Domänendienste für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
description: Active Directory-Domänendienste fungiert als Verzeichnisdienst für Windows Server 2003, Windows Server 2008, Windows Server 2012 und Windows Server 2012 R2-Netzwerke. Active Directory-Domänendienste dient auch als Grundlage für die Erstellung der Skype for Business Server-Sicherheitsinfrastruktur. In diesem Abschnitt wird beschrieben, wie Skype for Business Server die Active Directory-Domänendienste zum Erstellen einer vertrauenswürdigen Umgebung für Chats, Webkonferenzen, Medien und Sprachanrufe verwendet. Details zum Vorbereiten Ihrer Umgebung für Active Directory-Domänendienste finden Sie unter Installieren von Skype for Business Server in der Bereitstellungsdokumentation. Details zur Rolle der Active Directory-Domänendienste in Windows Server-Netzwerken finden Sie in der Dokumentation zur Version des verwendeten Betriebssystems.
ms.openlocfilehash: 4458d49bf2f57284ac29c68bb40f3979761d5c50
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297008"
---
# <a name="active-directory-domain-services-for-skype-for-business-server"></a>Active Directory-Domänendienste für Skype for Business Server
 
Active Directory-Domänendienste fungiert als Verzeichnisdienst für Windows Server 2003, Windows Server 2008, Windows Server 2012 und Windows Server 2012 R2-Netzwerke. Active Directory-Domänendienste dient auch als Grundlage für die Erstellung der Skype for Business Server-Sicherheitsinfrastruktur. In diesem Abschnitt wird beschrieben, wie Skype for Business Server die Active Directory-Domänendienste zum Erstellen einer vertrauenswürdigen Umgebung für Chats, Webkonferenzen, Medien und Sprachanrufe verwendet. Details zum Vorbereiten Ihrer Umgebung für Active Directory-Domänendienste finden Sie unter [Installieren von Skype for Business Server](../../deploy/install/install.md) in der Bereitstellungsdokumentation. Details zur Rolle der Active Directory-Domänendienste in Windows Server-Netzwerken finden Sie in der Dokumentation zur Version des verwendeten Betriebssystems.
  
Skype for Business Server verwendet Active Directory-Domänendienste zum Speichern von:
  
- Globale Einstellungen, die von allen Servern mit Skype for Business Server in einer Gesamtstruktur benötigt werden.
    
- Dienstinformationen, die die Rollen aller Server, die Skype for Business Server ausführen, in einer Gesamtstruktur identifizieren.
    
- Einige Benutzereinstellungen
    
## <a name="active-directory-infrastructure"></a>Active Directory-Infrastruktur

Zu den Infrastrukturanforderungen für Active Directory gehören die folgenden:
  
- Betriebssystemanforderungen für Domänencontroller
    
- Anforderungen für die Domänen- und Gesamtstrukturfunktionsebene
    
- Anforderungen für die globale Katalogdomäne
    
Einzelheiten hierzu finden Sie unter [Umweltanforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) oder [Server Anforderungen für Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
  
## <a name="universal-groups"></a>Universelle Gruppen

Während der Vorbereitung der Gesamtstruktur erstellt Skype for Business Server verschiedene universelle Gruppen in Active Directory-Domänendiensten, die über die Berechtigung zum Zugriff auf und Verwalten globaler Einstellungen und Dienste verfügen. Zu diesen Gruppen zählen die folgenden:
  
- **Administrative Gruppen:** Diese Gruppen definieren die grundlegenden Administratorrollen für ein Skype for Business Server-Netzwerk. Während der Gesamtstrukturvorbereitung werden diese Administratorgruppen zu den Skype for Business Server-Infrastrukturgruppen hinzugefügt.
    
- **Dienstgruppen:** Diese Gruppen sind Dienstkonten, die für den Zugriff auf verschiedene Dienste erforderlich sind, die von Skype for Business Server bereitgestellt werden.
    
- **Infrastrukturgruppen:** Diese Gruppen bieten die Berechtigung für den Zugriff auf bestimmte Bereiche der Skype for Business Server-Infrastruktur. Sie dienen als Komponenten von administrativen Gruppen und Sie sollten sie weder ändern noch ihnen direkt Nutzer hinzufügen. Während der Gesamtstrukturvorbereitung werden den entsprechenden Infrastrukturgruppen bestimmte Dienst- und Administrationsgruppen hinzugefügt.
    
Details zu den spezifischen universellen Gruppen, die beim Vorbereiten von AD für Skype for Business Server erstellt wurden, sowie zu den Dienst-und Verwaltungsgruppen, die den Infrastrukturgruppen hinzugefügt werden, finden Sie unter Änderungen, die [von der Gesamtstrukturvorbereitung in Skype for Business vorgenommen wurden. Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) in der Bereitstellungsdokumentation.
  
> [!NOTE]
> Skype for Business Server unterstützt universelle Gruppen in Windows Server 2012 sowie Windows Server 2003-Betriebssysteme für Domänencontroller. Mitglieder universeller Gruppen können andere Gruppen und Konten aus beliebigen Domänen in der Domänen- oder Gesamtstruktur umfassen und über Berechtigungen für beliebige Domänen in der Domänen- oder Gesamtstruktur verfügen. Die Unterstützung für universelle Gruppen in Verbindung mit der Administrator Delegierung vereinfacht die Verwaltung einer Skype for Business Server-Bereitstellung. Beispielsweise ist es nicht erforderlich, eine Domäne einer anderen hinzuzufügen, um einem Administrator die Verwaltung beider Domänen zu ermöglichen. 
  
## <a name="role-based-access-control"></a>Rollenbasierte Zugriffssteuerung

Zusätzlich zum Erstellen von Gruppen für universelle Dienste und Administratoren sowie zum Hinzufügen von Dienst-und Verwaltungsgruppen zu den entsprechenden universellen Gruppen erstellt die Gesamtstrukturvorbereitung auch Rollenbasierte Zugriffssteuerungsgruppen. Details zu den von der Gesamtstrukturvorbereitung erstellten speziellen RBAC-Gruppen finden Sie unter Änderungen, die [von der Gesamtstrukturvorbereitung in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) in der Bereitstellungsdokumentation vorgenommen wurden. Weitere Informationen zu RBAC-Gruppen finden Sie unter [rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) für Skype for Business Server](role-based-access-control-rbac.md).
  
## <a name="access-control-entries-aces-and-inheritance"></a>Zugriffssteuerungseinträge (Access Control Entries,ACEs) und Vererbung

Bei der Gesamtstrukturvorbereitung werden sowohl private als auch öffentliche ACEs erstellt und ACEs zu den erstellten universellen Gruppen hinzugefügt. Es werden bestimmte private ACEs auf dem Container für globale Einstellungen erstellt, der von Skype for Business Server verwendet wird. Dieser Container wird nur von Skype for Business Server verwendet und befindet sich entweder im Konfigurationscontainer oder im System Container in der Stammdomäne, je nachdem, wo Sie die globalen Einstellungen speichern.
  
Beim Schritt zur Domänenvorbereitung werden universellen Gruppen die erforderlichen ACEs (Access Control Entries, Zugriffssteuerungseinträge) hinzugefügt, über die Berechtigungen zum Hosten und Verwalten von Benutzern in der Domäne gewährt werden. Bei der Domänenvorbereitung werden ACEs im Domänenstamm und in drei integrierten Containern erstellt: für Benutzer, Computer und Domänencontroller.
  
Details zu den öffentlichen ACEs, die von der Gesamtstrukturvorbereitung und Domänenvorbereitung erstellt und hinzugefügt wurden, finden Sie unter Änderungen, die von der Vorbereitung der [Gesamtstruktur in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) vorgenommen wurden, und Änderungen, die [von der Domänenvorbereitung in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-domain-preparation.md) im Bereitstellungsdokumentation
  
Organisationen Sperren häufig Active Directory-Domänendienste (AD DS), um Sicherheitsrisiken zu minimieren. Eine gesperrte Active Directory-Umgebung kann jedoch die von Skype for Business Server benötigten Berechtigungen einschränken. Dazu kann das Entfernen von ACEs aus Containern und Organisationseinheiten und das Deaktivieren der Vererbung von Berechtigungen für Nutzer-, Kontakt-, InetOrgPerson- oder Computerobjekten gehören. In einer gesperrten Active Directory-Umgebung müssen Berechtigungen für Container und OUs, für die Sie erforderlich sind, manuell festgelegt werden.
  
## <a name="server-information"></a>Serverinformationen

Während der Aktivierung veröffentlicht Skype for Business Server Server Informationen an den drei folgenden Speicherorten in den Active Directory-Domänendiensten:
  
- Einen Dienstverbindungspunkt (Service Connection Point, SCP) auf jedem Active Directory-Computerobjekt, das einem physikalischen Computer entspricht, auf dem Skype for Business Server installiert ist.
    
- Serverobjekte, die im Container der Klasse **msRTCSIP-Pools** erstellt wurden
    
- Im Topologie-Generator angegebene vertrauenswürdige Server.
    
## <a name="service-connection-points"></a>Dienstverbindungspunkte

Jedes Skype for Business Server-Objekt in den Active Directory-Domänendiensten verfügt über einen SCP namens RTC Services, der wiederum eine Reihe von Attributen enthält, die jeden Computer identifizieren und die bereitgestellten Dienste angeben. Zu den wichtigsten SCP-Attributen zählen *servicednsname* , *serviceDNSNameType* , *serviceClassName* und *serviceBindingInformation* . Asset Management-Anwendungen von Drittanbietern können Serverinformationen bereitstellungsübergreifend abrufen, indem sie diese und andere Attribute von Dienstverbindungspunkten anfragen.
  
## <a name="active-directory-server-objects"></a>Active Directory-Server Objekte

Jede Skype for Business Server-Serverrolle verfügt über ein entsprechendes Active Directory-Objekt, dessen Attribute die Dienste definieren, die von dieser Rolle bereitgestellt werden. Wenn ein Standard Edition-Server aktiviert ist oder ein Enterprise Edition-Pool erstellt wird, erstellt Skype for Business Server ein neues **Attribut msRTCSIP-** Objekt im Container **Attribut msRTCSIP-Pools** . Die **msRTCSIP-Pool**-Klasse gibt den vollständig qualifizierten Domänennamen (FQDN) des Pools sowie die Verbindung zwischen den Front-End- und Back-End-Komponenten des Pools an. (Ein Standard Edition-Server wird als logischer Pool angesehen, dessen Front-und Back-Ends auf einem einzelnen Computer angeordnet sind.)
  
## <a name="trusted-servers"></a>Vertrauenswürdige Server

In Skype for Business Server sind vertrauenswürdige Server diejenigen, die beim Ausführen von Topology Builder und Veröffentlichen Ihrer Topologie angegeben werden. Die veröffentlichte Topologie wird einschließlich aller Serverinformationen im zentralen Verwaltungsspeicher gespeichert. Nur die im zentralen Verwaltungsspeicher definierten Server sind vertrauenswürdig. In Skype for Business Server ist ein vertrauenswürdiger Server einer, der die folgenden Kriterien erfüllt:
  
- Der FQDN des Servers ist in der im zentralen Verwaltungsspeicher gespeicherten Topologie enthalten.
    
- Der Server verfügt über ein gültiges Zertifikat von einer vertrauenswürdigen Zertifizierungsstelle. Einzelheiten hierzu finden Sie unter [Umweltanforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) oder [System Anforderungen für Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
    
Wird eins dieser Kriterien nicht erfüllt, ist der Server nicht vertrauenswürdig, und die Verbindung mit ihm wird abgelehnt. Diese doppelte Anforderung verhindert einen möglichen, wenn auch unwahrscheinlichen Angriff, bei dem ein nicht autorisierter Server versucht, den FQDN eines gültigen Servers zu übernehmen.
  
Damit Microsoft Office Communications Server 2007 R2 und Microsoft Office Communications Server 2007-Bereitstellungen mit Skype for Business Server-Servern kommunizieren können, erstellt Skype for Business Server während der Gesamtstrukturvorbereitung Container. für die Aufbewahrung von Listen mit vertrauenswürdigen Servern für frühere Versionen. In der folgenden Tabelle sind die für die Kompatibilität mit früheren Bereitstellungen erstellten Container beschrieben.
  
**Vertrauenswürdige Server Listen und deren Active Directory-Container zur Kompatibilität mit früheren Versionen**

|**Liste vertrauenswürdiger Server**|**Active Directory-Container**|
|:-----|:-----|
|Standard Edition-Server und Enterprise-Pool-Front-End-Server  <br/> |RTC Service/Global Settings  <br/> |
|Konferenzserver  <br/> |RTC Service/Trusted MCUs  <br/> |
|Webkomponentenserver  <br/> |RTC Service/TrustedWebComponentsServers  <br/> |
|Vermittlungsservers und Communicator Web Access-Server, Anwendungsserver, Registrierung mit QoE, A/V-Konferenzdienst (auch SIP-Server von Drittanbietern)  <br/> |RTC Service/Trusted Services  <br/> |
|Proxyserver  <br/> |Skype for Business Server unterstützt keine Abwärtskompatibilität für Proxy Server  <br/> |
   

## <a name="see-also"></a>Siehe auch

[Vorbereiten von Active Directory für Skype for Business Server](../../deploy/install/prepare-active-directory.md)
