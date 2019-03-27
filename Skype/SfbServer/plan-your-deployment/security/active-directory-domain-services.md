---
title: Active Directory-Domänendienste für Skype für Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
description: Active Directory-Domänendienste fungiert als Verzeichnisdienst für Windows Server 2003, Windows Server 2008, Windows Server 2012 und Windows Server 2012 R2-Netzwerke. Active Directory-Domänendienste dient auch als Grundlage für die die Skype Sicherheitsinfrastruktur Business Server erstellt wird. Der Zweck dieses Abschnitts wird beschrieben, wie Skype für Business Server Active Directory Domain Services verwendet, um eine vertrauenswürdige Umgebung für Sofortnachrichten, Konferenzen, Medien und VoIP zu erstellen. Ausführliche Informationen zum Vorbereiten der Umgebung für Active Directory Domain Services finden Sie unter Installieren von Skype Business Server in der Bereitstellungsdokumentation. Ausführliche Informationen zur Rolle der Active Directory-Domänendienste in Windows Server-Netzwerken finden Sie unter Dokumentation für die Version des Betriebssystems, die Sie verwenden.
ms.openlocfilehash: 1664f3b354078c79429b20e7654b363ce9fccb7f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892385"
---
# <a name="active-directory-domain-services-for-skype-for-business-server"></a>Active Directory-Domänendienste für Skype für Business Server
 
Active Directory-Domänendienste fungiert als Verzeichnisdienst für Windows Server 2003, Windows Server 2008, Windows Server 2012 und Windows Server 2012 R2-Netzwerke. Active Directory-Domänendienste dient auch als Grundlage für die die Skype Sicherheitsinfrastruktur Business Server erstellt wird. Der Zweck dieses Abschnitts wird beschrieben, wie Skype für Business Server Active Directory Domain Services verwendet, um eine vertrauenswürdige Umgebung für Sofortnachrichten, Konferenzen, Medien und VoIP zu erstellen. Ausführliche Informationen zum Vorbereiten der Umgebung für Active Directory Domain Services finden Sie in der Bereitstellungsdokumentation [Skype für Business Server installieren](../../deploy/install/install.md) . Ausführliche Informationen zur Rolle der Active Directory-Domänendienste in Windows Server-Netzwerken finden Sie unter Dokumentation für die Version des Betriebssystems, die Sie verwenden.
  
Skype für Business Server wird zum Speichern von Active Directory Domain Services verwendet:
  
- Globale Einstellungen, die alle Server mit Skype für Business Server in einer Gesamtstruktur erforderlich.
    
- Dienstinformationen, die die Rollen aller Server mit Skype für Business Server in einer Gesamtstruktur identifiziert.
    
- Einige Benutzereinstellungen
    
## <a name="active-directory-infrastructure"></a>Active Directory-Infrastruktur

Die folgenden: Anforderungen an die Netzwerkinfrastruktur für Active Directory
  
- Betriebssystemanforderungen für Domänencontroller
    
- Anforderungen für die Domänen- und Gesamtstrukturfunktionsebene
    
- Anforderungen für die globale Katalogdomäne
    
Weitere Informationen hierzu finden Sie unter [umgebungsanforderungen für Skype für Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) oder [Anforderungen für Skype für Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
  
## <a name="universal-groups"></a>Universelle Gruppen

Während der Vorbereitung der Gesamtstruktur erstellt Skype für Business Server mehrere universelle Gruppen innerhalb der Active Directory Domain Services, die über die Berechtigung zum zugreifen und diese globale Einstellungen und Dienste verwalten. Zu diesen Gruppen zählen die folgenden:
  
- **Administrative Gruppen:** Diese Gruppen definieren die grundlegenden Administratorrollen für ein Skype für Business Server-Netzwerk. Während der Vorbereitung der Gesamtstruktur werden diese Administratorgruppen Skype für Infrastrukturgruppen Business Server hinzugefügt.
    
- **Dienstgruppen:** Diese Gruppen sind Dienstkonten, die Zugriff auf verschiedene Dienste von Skype für Business Server bereitgestellten erforderlich sind.
    
- **Infrastrukturgruppen:** Diese Gruppen bieten die Zugriffsberechtigung für bestimmte Bereiche der Skype für Business Server-Infrastruktur. Sie dienen als Komponenten von administrativen Gruppen und Sie sollten sie weder ändern noch ihnen direkt Nutzer hinzufügen. Während der Gesamtstrukturvorbereitung werden den entsprechenden Infrastrukturgruppen bestimmte Dienst- und Administrationsgruppen hinzugefügt.
    
Ausführliche Informationen zu universellen Gruppen erstellt, bei der Vorbereitung von Active Directory für Skype für Business Server als auch die Dienst- und Administrationsgruppen, die an die Infrastrukturgruppen hinzugefügt werden, finden Sie unter [Änderungen, die durch die Vorbereitung der Gesamtstruktur in Skype für Unternehmen Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) in der Bereitstellungsdokumentation.
  
> [!NOTE]
> Skype für Business Server unterstützt die universellen Gruppen in der Windows Server 2012 sowie Windows Server 2003-Betriebssysteme für Domänencontroller. Mitglieder universeller Gruppen können andere Gruppen und Konten aus beliebigen Domänen in der Domänen- oder Gesamtstruktur umfassen und über Berechtigungen für beliebige Domänen in der Domänen- oder Gesamtstruktur verfügen. Unterstützung universeller Gruppen in Verbindung mit der Delegierung, vereinfacht die Verwaltung von einem Skype für Business Server-Bereitstellung. Beispielsweise ist es nicht erforderlich, eine Domäne einer anderen hinzuzufügen, um einem Administrator die Verwaltung beider Domänen zu ermöglichen. 
  
## <a name="role-based-access-control"></a>Rollenbasierte Zugriffssteuerung

Zusätzlich zu universelle Dienst- und Administrationsgruppen erstellen und Hinzufügen von Dienst- und Verwaltungsgruppen den entsprechenden universelle Gruppen, Vorbereitung der Gesamtstruktur außerdem die Role-Based Access Control (RBAC) Gruppen erstellt. Ausführliche Informationen zu RBAC Gruppen von der Gesamtstruktur erstellt finden Sie unter [Änderungen vorgenommen, die von der gesamtstrukturvorbereitung in Skype für Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) in der Bereitstellungsdokumentation. Weitere Informationen zu RBAC-Gruppen finden Sie unter [Role-based Access Control (RBAC) Skype für Business Server](role-based-access-control-rbac.md).
  
## <a name="access-control-entries-aces-and-inheritance"></a>Zugriffssteuerungseinträge (Access Control Entries,ACEs) und Vererbung

Bei der Gesamtstrukturvorbereitung werden sowohl private als auch öffentliche ACEs erstellt und ACEs zu den erstellten universellen Gruppen hinzugefügt. Bestimmte private ACEs erstellt auf den Container für globale Einstellungen von Skype für Business Server verwendet wird. Dieser Container wird nur von Skype für Business Server verwendet und befindet sich entweder im Konfigurationscontainer oder dem Systemcontainer in der Stammdomäne, je nachdem, wo Sie globale Einstellungen gespeichert werden.
  
Beim Schritt zur Domänenvorbereitung werden universellen Gruppen die erforderlichen ACEs (Access Control Entries, Zugriffssteuerungseinträge) hinzugefügt, über die Berechtigungen zum Hosten und Verwalten von Benutzern in der Domäne gewährt werden. Bei der Domänenvorbereitung werden ACEs im Domänenstamm und in drei integrierten Containern erstellt: für Benutzer, Computer und Domänencontroller.
  
Details zu den öffentlichen ACEs erstellt und von der gesamtstrukturvorbereitung domänenvorbereitung hinzugefügt, finden Sie unter [Änderungen vorgenommen, die von der gesamtstrukturvorbereitung in Skype für Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) und [Änderungen domänenvorbereitung in Skype für Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-domain-preparation.md) in der Dokumentation zur Bereitstellung.
  
Organisationen Sperren häufig auf Active Directory-Domänendienste (AD DS) zum Verringern von Sicherheitsrisiken. Eine gesperrten Active Directory-Umgebung kann jedoch die Berechtigungen beschränkt, die Skype für Business Server erforderlich sind. Dazu kann das Entfernen von ACEs aus Containern und Organisationseinheiten und das Deaktivieren der Vererbung von Berechtigungen für Nutzer-, Kontakt-, InetOrgPerson- oder Computerobjekten gehören. In einer gesperrten Active Directory-Umgebung müssen Berechtigungen festgelegt werden manuell auf Standardcontainer und OUs, die sie benötigen.
  
## <a name="server-information"></a>Serverinformationen

Während der Aktivierung veröffentlicht Skype für Business Server Serverinformationen an den drei folgenden Orten in Active Directory Domain Services:
  
- Ein Dienstverbindungspunkt (SCP) auf jedem Active Directory-Computerobjekt, das einem physischen Computer auf dem Skype für Business Server installiert ist.
    
- Serverobjekte, die im Container der Klasse **msRTCSIP-Pools** erstellt wurden
    
- Vertrauenswürdige Server im Topologie-Generator angegeben.
    
## <a name="service-connection-points"></a>Dienstverbindungspunkte

Jede Skype für Business Server-Objekts in Active Directory Domain Services hat SCP aufgerufen, RTC-Dienste, die wiederum eine Reihe von Attributen enthält, die einzelnen Computer, und geben Sie die Dienste, die es bereitstellt. Attribute sind zwischen den wichtiger SCP *ServiceDNSName* , *ServiceDNSNameType* , *ServiceClassname* und *ServiceBindingInformation* . Asset Management-Anwendungen von Drittanbietern können Serverinformationen bereitstellungsübergreifend abrufen, indem sie diese und andere Attribute von Dienstverbindungspunkten anfragen.
  
## <a name="active-directory-server-objects"></a>Active Directory-Serverobjekte

Jede Skype für Business Server-Rolle verfügt über ein entsprechendes Active Directory-Objekt, dessen Attribute, die von dieser Rolle bereitgestellten Dienste definieren. Darüber hinaus erstellt bei ein Standard Edition-Server aktiviert wird oder wenn Sie ein Enterprise Edition-Pool erstellt wird, Skype für Business Server ein neues Objekt **MsRTCSIP-Pool** in der **MsRTCSIP-Pools** -Container. Die **msRTCSIP-Pool**-Klasse gibt den vollständig qualifizierten Domänennamen (FQDN) des Pools sowie die Verbindung zwischen den Front-End- und Back-End-Komponenten des Pools an. (Standard Edition-Server wird als logischer Pool, dessen Front- und Back-Ends auf einem einzelnen Computer zusammengestellt werden, angesehen.)
  
## <a name="trusted-servers"></a>Vertrauenswürdige Server

In Skype für Business Server sind die vertrauenswürdige Servern derjenigen, die beim Ausführen des Topologie-Generator und Ihrer Topologie veröffentlichen angegeben. Die veröffentlichte Topologie wird einschließlich aller Serverinformationen im zentralen Verwaltungsspeicher gespeichert. Nur die im zentralen Verwaltungsspeicher definierten Server sind vertrauenswürdig. In Skype für Business Server ist ein vertrauenswürdiger Server eine, die die folgenden Kriterien erfüllt:
  
- Der FQDN des Servers ist in der im zentralen Verwaltungsspeicher gespeicherten Topologie enthalten.
    
- Der Server verfügt über ein gültiges Zertifikat von einer vertrauenswürdigen Zertifizierungsstelle. Weitere Informationen hierzu finden Sie unter [umgebungsanforderungen für Skype für Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) oder [Systemanforderungen für Skype für Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
    
Wird eins dieser Kriterien nicht erfüllt, ist der Server nicht vertrauenswürdig, und die Verbindung mit ihm wird abgelehnt. Diese doppelte Anforderung soll einen möglichen, wenn, Angriff, bei dem ein nicht autorisierter Server versucht FQDN eines gültigen Servers zu übernehmen.
  
Darüber hinaus erstellt zum Aktivieren von Microsoft Office Communications Server 2007 R2 und Microsoft Office Communications Server 2007-Bereitstellungen mit Skype für Business Server-Server kommunizieren Skype für Business Server Container während der Vorbereitung der Gesamtstruktur für das Halten von Listen mit vertrauenswürdigen Servern für frühere Versionen. In der folgenden Tabelle sind die für die Kompatibilität mit früheren Bereitstellungen erstellten Container beschrieben.
  
**Vertrauenswürdige Server-Listen und ihre Active Directory-Container für die Kompatibilität mit früheren Versionen**

|**Liste vertrauenswürdiger Server**|**Active Directory-container**|
|:-----|:-----|
|Standard Edition-Server und Enterprise-Pool-Front-End-Server  <br/> |RTC Service/Global Settings  <br/> |
|Konferenzserver  <br/> |RTC Service/Trusted MCUs  <br/> |
|Webkomponentenserver  <br/> |RTC Service/TrustedWebComponentsServers  <br/> |
|Vermittlungsservers und Communicator Web Access-Server, Anwendungsserver, Registrierung mit QoE, A/V-Konferenzdienst (auch SIP-Server von Drittanbietern)  <br/> |RTC Service/Trusted Services  <br/> |
|Proxyserver  <br/> |Skype für Business Server unterstützt keine Abwärtskompatibilität für Proxyserver  <br/> |
   

## <a name="see-also"></a>Siehe auch

[Vorbereiten von Active Directory für Skype für Business Server](../../deploy/install/prepare-active-directory.md)
