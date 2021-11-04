---
title: Active Directory-Domänendienste für Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
description: Active Directory Domain Services fungiert als Verzeichnisdienst für Windows Server 2003-, Windows Server 2008-, Windows Server 2012- und Windows Server 2012 R2-Netzwerke. Active Directory Domain Services dient auch als Grundlage, auf der die Skype for Business Server Sicherheitsinfrastruktur aufgebaut ist. In diesem Abschnitt wird beschrieben, wie Skype for Business Server Active Directory Domain Services verwendet, um eine vertrauenswürdige Umgebung für Chat, Webkonferenzen, Medien und VoIP zu erstellen. Ausführliche Informationen zum Vorbereiten Ihrer Umgebung für Active Directory Domain Services finden Sie unter Installieren Skype for Business Server in der Bereitstellungsdokumentation. Ausführliche Informationen zur Rolle der Active Directory-Domänendienste in Windows Server-Netzwerken finden Sie in der Dokumentation für die Version des von Ihnen verwendeten Betriebssystems.
ms.openlocfilehash: 496abf7f0210a1663c1158da56c8fb1cce66f068
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759467"
---
# <a name="active-directory-domain-services-for-skype-for-business-server"></a>Active Directory-Domänendienste für Skype for Business Server
 
Active Directory Domain Services fungiert als Verzeichnisdienst für Windows Server 2003-, Windows Server 2008-, Windows Server 2012- und Windows Server 2012 R2-Netzwerke. Active Directory Domain Services dient auch als Grundlage, auf der die Skype for Business Server Sicherheitsinfrastruktur aufgebaut ist. In diesem Abschnitt wird beschrieben, wie Skype for Business Server Active Directory Domain Services verwendet, um eine vertrauenswürdige Umgebung für Chat, Webkonferenzen, Medien und VoIP zu erstellen. Ausführliche Informationen zum Vorbereiten Ihrer Umgebung für Active Directory Domain Services finden Sie unter [Installieren Skype for Business Server](../../deploy/install/install.md) in der Bereitstellungsdokumentation. Ausführliche Informationen zur Rolle der Active Directory-Domänendienste in Windows Server-Netzwerken finden Sie in der Dokumentation für die Version des von Ihnen verwendeten Betriebssystems.
  
Skype for Business Server verwendet Active Directory-Domänendienste zum Speichern:
  
- Globale Einstellungen, die für alle Server, die Skype for Business Server in einer Gesamtstruktur ausgeführt werden, erforderlich sind.
    
- Dienstinformationen, die die Rollen aller Server identifizieren, auf denen Skype for Business Server in einer Gesamtstruktur ausgeführt wird.
    
- Einige Benutzereinstellungen
    
## <a name="active-directory-infrastructure"></a>Active Directory-Infrastruktur

Für Active Directory gelten die folgenden Infrastrukturanforderungen:
  
- Betriebssystemanforderungen für Domänencontroller
    
- Anforderungen bezüglich der Funktionsebene der Domäne und der Gesamtstruktur
    
- Domänenanforderungen bezüglich des globalen Katalogs
    
Ausführliche Informationen finden Sie unter ["Environmental requirements for Skype for Business Server 2015"](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) oder ["Server requirements for Skype for Business Server 2019".](../../../SfBServer2019/plan/system-requirements.md)
  
## <a name="universal-groups"></a>Universelle Gruppen

Während der Vorbereitung der Gesamtstruktur erstellt Skype for Business Server verschiedene universelle Gruppen innerhalb von Active Directory-Domänendiensten, die über die Berechtigung zum Zugriff auf und die Verwaltung globaler Einstellungen und Dienste verfügen. Dazu gehören folgende universelle Gruppen:
  
- **Administrative Gruppen**. Diese Gruppen definieren die grundlegenden Administratorrollen für ein Skype for Business Server Netzwerk. Während der Gesamtstrukturvorbereitung werden diese Administratorgruppen Skype for Business Server Infrastrukturgruppen hinzugefügt.
    
- **Dienstgruppen**. Diese Gruppen sind Dienstkonten, die für den Zugriff auf verschiedene von Skype for Business Server bereitgestellte Dienste erforderlich sind.
    
- **Infrastrukturgruppen**. Diese Gruppen erteilen die Berechtigung für den Zugriff auf bestimmte Bereiche der Skype for Business Server-Infrastruktur. Es sollten keine Infrastrukturgruppen geändert oder Benutzer direkt zu ihnen hinzugefügt werden. Während der Gesamtstrukturvorbereitung werden bestimmte Dienst- und Verwaltungsgruppen zu den entsprechenden Infrastrukturgruppen hinzugefügt.
    
Ausführliche Informationen zu den spezifischen universellen Gruppen, die bei der Vorbereitung von AD für Skype for Business Server erstellt wurden, sowie zu den Dienst- und Verwaltungsgruppen, die den Infrastrukturgruppen hinzugefügt werden, finden Sie unter Änderungen, die durch die [Gesamtstrukturvorbereitung in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) in der Bereitstellungsdokumentation vorgenommen wurden.
  
> [!NOTE]
> Skype for Business Server unterstützt die universellen Gruppen im Windows Server 2012 sowie Windows Server 2003-Betriebssysteme für Domänencontroller. Mitglieder universeller Gruppen können andere Gruppen und Konten aus beliebigen Domänen in der Domänen- oder Gesamtstruktur umfassen und über Berechtigungen für beliebige Domänen in der Domänen- oder Gesamtstruktur verfügen. Die universelle Gruppenunterstützung in Kombination mit der Administratordelegierung vereinfacht die Verwaltung einer Skype for Business Server Bereitstellung. Beispielsweise ist es nicht erforderlich, eine Domäne einer anderen Domäne hinzuzufügen, um einem Administrator die Verwaltung beider Domänen zu ermöglichen. 
  
## <a name="role-based-access-control"></a>Rollenbasierte Zugriffssteuerung

Zusätzlich zum Erstellen von universellen Diensten und Verwaltungsgruppen und hinzufügen von Dienst- und Verwaltungsgruppen zu den entsprechenden universellen Gruppen erstellt die Gesamtstrukturvorbereitung auch Role-Based RBAC-Gruppen (Access Control). Ausführliche Informationen zu den spezifischen RBAC-Gruppen, die durch die Gesamtstrukturvorbereitung erstellt wurden, finden Sie unter Änderungen, die durch die [Gesamtstrukturvorbereitung in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) in der Bereitstellungsdokumentation vorgenommen wurden. Weitere Informationen zu RBAC-Gruppen finden Sie unter [Rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) für Skype for Business Server](role-based-access-control-rbac.md).
  
## <a name="access-control-entries-aces-and-inheritance"></a>Zugriffssteuerungseinträge und Vererbung

Bei der Gesamtstrukturvorbereitung werden sowohl private als auch öffentliche Zugriffssteuerungseinträge (Access Control Entries, ACEs) erstellt sowie ACEs für die erstellten universellen Gruppen hinzugefügt. Es erstellt bestimmte private ACEs im globalen Einstellungscontainer, der von Skype for Business Server verwendet wird. Dieser Container wird nur von Skype for Business Server verwendet und befindet sich entweder im Konfigurationscontainer oder im Systemcontainer in der Stammdomäne, je nachdem, wo Sie globale Einstellungen speichern.
  
Beim Schritt zur Domänenvorbereitung werden universellen Gruppen die erforderlichen Zugriffssteuerungseinträge (Access Control Entries, ACEs) hinzugefügt, über die Berechtigungen zum Hosten und Verwalten von Benutzern in der Domäne gewährt werden. Bei der Domänenvorbereitung werden ACEs im Domänenstamm und in drei integrierten Containern erstellt: für Benutzer, Computer und Domänencontroller.
  
Ausführliche Informationen zu den öffentlichen ACEs, die durch die Gesamtstrukturvorbereitung und die Domänenvorbereitung erstellt und hinzugefügt wurden, finden Sie unter Änderungen, die durch die [Gesamtstrukturvorbereitung in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) vorgenommen wurden, und Änderungen, die [von der Domänenvorbereitung in Skype for Business Server in](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-domain-preparation.md) der Bereitstellungsdokumentation vorgenommen wurden.
  
In Organisationen werden die Active Directory-Domänendienste (Active Directory Domain Services, AD DS) häufig gesperrt, um Sicherheitsrisiken nach Möglichkeit auszuschließen. Eine gesperrte Active Directory-Umgebung kann jedoch die Berechtigungen einschränken, die Skype for Business Server benötigen. Dies kann das Entfernen von ACEs aus Containern und Organisationseinheiten (Organizational Units, OUs) und das Deaktivieren der Vererbung von Berechtigungen für Benutzer-, Kontakt-, InetOrgPerson- oder Computerobjekte beinhalten. In einer gesperrten Active Directory-Umgebung müssen Berechtigungen manuell für die entsprechenden Container und Organisationseinheiten festgelegt werden.
  
## <a name="server-information"></a>Serverinformationen

Während der Aktivierung veröffentlicht Skype for Business Server Serverinformationen an den drei folgenden Speicherorten in Active Directory Domain Services:
  
- Ein Dienstverbindungspunkt (SCP) auf jedem Active Directory-Computerobjekt, das einem physischen Computer entspricht, auf dem Skype for Business Server installiert ist.
    
- Serverobjekte, die im Container der **msRTCSIP-Pools**-Klasse erstellt wurden
    
- Im Topologie-Generator angegebene vertrauenswürdige Server.
    
## <a name="service-connection-points"></a>Dienstverbindungspunkte

Jedes Skype for Business Server-Objekt in Active Directory Domain Services verfügt über einen SCP namens "RTC Services", der wiederum eine Reihe von Attributen enthält, die jeden Computer identifizieren und die von ihm bereitgestellten Dienste angeben. Zu den wichtigeren SCP-Attributen zählen *"serviceDNSName",* *"serviceDNSNameType",* *"serviceClassname"* und *"serviceBindingInformation".* Ressourcenverwaltungsanwendungen von Drittanbietern können Serverinformationen in einer Bereitstellung abrufen, indem sie diese und andere SCP-Attribute abfragen.
  
## <a name="active-directory-server-objects"></a>Active Directory-Serverobjekte

Jede Skype for Business Server Serverrolle verfügt über ein entsprechendes Active Directory-Objekt, dessen Attribute die von dieser Rolle bereitgestellten Dienste definieren. Wenn ein Standard Edition Server aktiviert oder ein Enterprise Edition Pool erstellt wird, erstellt Skype for Business Server außerdem ein neues **MsRTCSIP-Pool-Objekt** im **Container "msRTCSIP-Pools".** In der **msRTCSIP-Pool**-Klasse werden der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Pools und die Zuordnung zwischen Front-End- und Back-End-Komponenten des Pools festgelegt. (Ein Standard Edition-Server wird als logischer Pool betrachtet, dessen Front- und Back-Ends gemeinsam auf einem einzigen Computer ausgeführt werden.)
  
## <a name="trusted-servers"></a>Vertrauenswürdige Server

In Skype for Business Server sind vertrauenswürdige Server diejenigen, die angegeben werden, wenn Sie den Topologie-Generator ausführen und Ihre Topologie veröffentlichen. Die veröffentlichte Topologie, einschließlich aller Serverinformationen, wird im zentralen Verwaltungsspeicher gespeichert. Nur im zentralen Verwaltungsspeicher definierte Server sind vertrauenswürdig. In Skype for Business Server erfüllt ein vertrauenswürdiger Server die folgenden Kriterien:
  
- Der vollqualifizierte Domänenname (FQDN) des Servers ist in der im zentralen Verwaltungsspeicher gespeicherten Topologie vorhanden.
    
- Der Server verfügt über ein gültiges Zertifikat von einer vertrauenswürdigen Zertifizierungsstelle. Ausführliche Informationen finden Sie unter ["Environmental requirements for Skype for Business Server 2015"](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) oder ["System requirements for Skype for Business Server 2019".](../../../SfBServer2019/plan/system-requirements.md)
    
Wenn eines dieser Kriterien nicht zutrifft, gilt der Server nicht als vertrauenswürdig und es wird keine Verbindung damit hergestellt. Diese doppelte Anforderung verhindert einen möglichen, wenn auch unwahrscheinlichen Angriff, bei dem ein nicht autorisierter Server versucht, den FQDN eines gültigen Servers zu übernehmen.
  
Um Microsoft Office Communications Server 2007 R2- und Microsoft Office Communications Server 2007-Bereitstellungen für die Kommunikation mit Skype for Business Server Servern zu ermöglichen, erstellt Skype for Business Server container während der Gesamtstruktur. Vorbereitung für das Speichern von Listen vertrauenswürdiger Server für frühere Versionen. In der folgenden Tabelle werden die Container beschrieben, die erstellt werden, um die Kompatibilität mit früheren Bereitstellungen zu ermöglichen.
  
**Listen mit vertrauenswürdigen Servern und ihre entsprechenden Active Directory-Container für die Kompatibilität mit vorherigen Versionen**

|**Listen mit vertrauenswürdigen Servern**|**Active Directory-Container**|
|:-----|:-----|
|Standard Edition-Server und Front End-Server von Enterprise-Pools  <br/> |RTC-Dienst/Globale Einstellungen  <br/> |
|Konferenzserver  <br/> |RTC-Dienst/Vertrauenswürdige MCUs  <br/> |
|Webkomponentenserver  <br/> |RTC-Dienst/TrustedWebComponentsServers  <br/> |
|Vermittlungsserver und Communicator Web Access-Server, Anwendungsserver, Registrierungsstelle mit QoE, A/V-Konferenzdienst (auch SIP-Server von Drittanbietern)  <br/> |RTC-Dienst/Vertrauenswürdige Dienste  <br/> |
|Proxyserver  <br/> |Skype for Business Server unterstützt keine Abwärtskompatibilität für Proxyserver  <br/> |
   

## <a name="see-also"></a>Weitere Informationen

[Vorbereiten von Active Directory für Skype for Business Server](../../deploy/install/prepare-active-directory.md)
