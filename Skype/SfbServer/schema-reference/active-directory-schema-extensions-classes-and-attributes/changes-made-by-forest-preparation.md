---
title: Änderungen, die durch die Vorbereitung der Gesamtstruktur in Skype für Business Server
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
description: Dieser Abschnitt beschreibt die globalen Einstellungen und Objekte und der universellen Dienst- und Administrationsgruppen, die durch die gesamtstrukturvorbereitung erstellt werden.
ms.openlocfilehash: 3e37948cae33412ac028d5190c780d6bee5aeeb2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="changes-made-by-forest-preparation-in-skype-for-business-server"></a>Änderungen, die durch die Vorbereitung der Gesamtstruktur in Skype für Business Server
 
Dieser Abschnitt beschreibt die globalen Einstellungen und Objekte und der universellen Dienst- und Administrationsgruppen, die durch die gesamtstrukturvorbereitung erstellt werden.
  
## <a name="active-directory-global-settings-and-objects"></a>Active Directory globale Einstellungen und Objekte

Wenn Sie globale Einstellungen im Konfigurationscontainer speichern, (wie die Groß-/Kleinschreibung für alle neuen Skype für Business Server-Bereitstellungen ist), die Vorbereitung der Gesamtstruktur verwendet den vorhandenen Container Services und fügt ein Objekt **RTC Service** unter der Configuration\Services -Objekt. Unter dem Objekt RTC Service fügt die gesamtstrukturvorbereitung ein **Global Settings** -Objekt vom Typ MsRTCSIP-GlobalContainer hinzu. Das globalen Einstellungen-Objekt enthält alle Einstellungen, die für die Skype für Business Server-Bereitstellung gelten. Wenn Sie globale Einstellungen im Systemcontainer speichern, verwendet der Vorbereitung der Gesamtstruktur ein Microsoft-Container unter Systemcontainer der Stammdomäne und ein Objekt RTC Service unter dem System\Microsoft-Objekt.
  
Vorbereitung der Gesamtstruktur fügt außerdem ein neues Objekt **MsRTCSIP-Domain** für die Stammdomäne, in der das Verfahren ausgeführt wird.
  
## <a name="active-directory-universal-service-and-administration-groups"></a>Active Directory universelle Dienst- und Verwaltungsgruppen

Vorbereitung der Gesamtstruktur erstellt universelle Gruppen basierend auf den, die von Ihnen angegebenen Domäne und fügt Zugriffssteuerungseinträge (ACEs) für diese Gruppen hinzu. Dieser Schritt erstellt die universellen Gruppen in den benutzercontainern der Domäne, die Sie angeben. 
  
Universelle Gruppen können Administratoren zugreifen und diese globale Einstellungen und Dienste verwalten. Vorbereitung der Gesamtstruktur fügt die folgenden Arten von universellen Gruppen:
  
- **Administrative Gruppen** Diese Gruppen werden Administratorrollen für ein Skype für Business Server-Netzwerk definiert.
    
- **Infrastrukturgruppen** Diese Gruppen bieten die Zugriffsberechtigung für bestimmte Bereiche der Skype für Business Server-Infrastruktur. Sie fungieren als Komponenten der administrativen Gruppen. Sie sollten nicht diese Gruppen ändern oder Hinzufügen von Benutzern direkt an.
    
- **Dienstgruppen** Diese Gruppen sind Dienstkonten, die erforderlich sind, auf verschiedenen Skype für Business Server-Dienste zugreifen.
    
In der folgenden Tabelle werden die administrativen Gruppen beschrieben.
  
**Administrative Gruppen, die während der Vorbereitung der Gesamtstruktur erstellt**

|**Administrative Gruppe**|**Beschreibung**|
|:-----|:-----|
|"RTCUniversalServerAdmins"  <br/> |Ermöglicht Mitgliedern das Verwalten von Server und pooleinstellungen, darunter alle Serverrollen, globalen Einstellungen und Benutzer.  <br/> |
|RTCUniversalUserAdmins  <br/> |Ermöglicht Mitgliedern das Verwalten von benutzereinstellungen und das Verschieben von Benutzern von einem Server oder Pool in einen anderen.  <br/> |
|RTCUniversalReadOnlyAdmins  <br/> |Ermöglicht Mitgliedern das Lesen von Server-, Pool- und User Settings.  <br/> |
   
In der folgenden Tabelle werden die Infrastrukturgruppen beschrieben.
  
**Infrastrukturgruppen, die während der Vorbereitung der Gesamtstruktur erstellt**

|**Infrastrukturgruppe**|**Beschreibung**|
|:-----|:-----|
|RTCUniversalGlobalWriteGroup  <br/> |Gewährt Schreibzugriff auf die globalen Einstellungsobjekte für Skype für Business Server.  <br/> |
|"Rtcuniversalglobalreadonlygroup"  <br/> |Gewährt schreibgeschützten Zugriff auf die globalen Einstellungsobjekte für Skype für Business Server.  <br/> |
|"RTCuniversalUserReadOnlyGroup"  <br/> |Gewährt schreibgeschützten Zugriff auf die Skype für Business Server-benutzereinstellungen.  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Gewährt schreibgeschützten Zugriff auf die Skype für Business Server-Einstellungen. Diese Gruppe hat keinen Zugriff auf die Einstellungen auf Poolebene, sondern lediglich auf Einstellungen für einen einzelnen Server.  <br/> |
|RTCUniversalSBATechnicians  <br/> |Gewährt schreibgeschützten Zugriff auf die Skype für die Business-Serverkonfiguration und werden während der Installation in der lokalen Administratorgruppe der survivable Branch Appliances eingefügt.  <br/> |
   
In der folgenden Tabelle werden die Dienstgruppen beschrieben.
  
**Dienstgruppen, die während der Vorbereitung der Gesamtstruktur erstellt**

|**Dienstgruppe**|**Beschreibung**|
|:-----|:-----|
|RTCHSUniversalServices  <br/> |Enthält Dienstkonten, die zum Ausführen von Front-End-Server und Standard Edition-Servern verwendet. Diese Gruppe ermöglicht Servern Lese-/Schreibzugriff auf Skype Business Server Globale Einstellungen und Active Directory-Benutzerobjekte.  <br/> |
|RTCComponentUniversalServices  <br/> |Enthält Dienstkonten, die zur Ausführung / V-Konferenzserver, Webdienste, Mediation Server, Archivierungsserver und Monitoring Server.  <br/> |
|RTCProxyUniversalServices  <br/> |Enthält Dienstkonten, die zum Ausführen von Skype für Business Server Edge-Server verwendet.  <br/> |
|RTCUniversalConfigReplicator  <br/> |Enthält Server, die teilnehmen können Skype für die Replikation für Business Server Central Management-Speicher.  <br/> |
|RTCSBAUniversalServices  <br/> |Gewährt schreibgeschützten Zugriff auf die Skype für Business Server-Einstellungen, ermöglicht aber auch die Konfiguration für die Installation einer survivable Branch Server- und survivable Branch Appliance-Bereitstellung.  <br/> |
   
Klicken Sie dann die Vorbereitung der Gesamtstruktur werden die entsprechenden Infrastrukturgruppen wie folgt Dienst- und Administrationsgruppen hinzugefügt:
  
- RTCUniversalServerAdmins wird RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup und RTCUniversalUserReadOnlyGroup hinzugefügt.
    
- RTCUniversalUserAdmins wird als Mitglied von RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup und RTCUniversalUserReadOnlyGroup hinzugefügt.
    
- RTCHSUniversalServices, RTCComponentUniversalServices und RTCUniversalReadOnlyAdmins werden als Mitglieder von RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup und RTCUniversalUserReadOnlyGroup hinzugefügt.
    
Vorbereitung der Gesamtstruktur wird auch die folgenden rollenbasierten Zugriffssteuerung (RBAC) Gruppen erstellt:
  
- "Csadministrator"
    
- Rolle "csarchivingadministrator"
    
- "Cshelpdesk"
    
- CSLocationAdministrator
    
- CSResponseGroupAdministrator
    
- CSServerAdministrator
    
- "CsUserAdministrator"
    
- CSViewOnlyAdministrator
    
- "Csvoiceadministrator"
    
- CsPersistentChatAdministator
    
- CsResponseGroupManager
    
Ausführliche Informationen zu RBAC-Rollen und die Aufgaben für die einzelnen zulässig finden Sie unter [Role-Based Access Control](http://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) in der Planungsdokumentation.
  
Vorbereitung der Gesamtstruktur werden sowohl private als auch öffentliche ACEs erstellt. Private ACEs erstellt auf den Container für globale Einstellungen von Skype für Business Server verwendet wird. Dieser Container wird nur von Skype für Business Server verwendet und befindet sich entweder im Konfigurationscontainer oder dem Systemcontainer in der Stammdomäne, je nachdem, wo Sie globale Einstellungen gespeichert werden. Nach der Vorbereitung der Gesamtstruktur erstellten öffentlichen ACEs sind in der folgenden Tabelle aufgeführt.
  
**Von der Gesamtstrukturvorbereitung erstellten öffentlichen ACEs**

|**ACE**|**"Rtcuniversalglobalreadonlygroup"**|
|:-----|:-----|
|Der Stammdomäne lesen (nicht vererbt) Systemcontainer**\*** <br/> |X  <br/> |
|DisplaySpecifiers-Container der Konfiguration lesen (nicht vererbt)  <br/> |X  <br/> |
   
> [!NOTE]
> **\***ACEs, die nicht vererbt werden, gewähren keinen Zugriff auf untergeordnete Objekte im betreffenden Container. ACEs, die vererbt werden, gewähren Zugriff auf untergeordnete Objekte im betreffenden Container. 
  
Auf den Konfigurationscontainer unter Konfigurationsnamenskontext führt der Vorbereitung der Gesamtstruktur die folgenden Aufgaben:
  
- Hinzufügen eines Eintrags **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** für die Seite **RTC Property** unter den Attributen AdminContextMenu und adminpropertypages der Sprache anzeigebezeichners für Benutzer, Kontakte und InetOrgPersons (z. B. CN = User-Display, CN = 409,CN = DisplaySpecifiers).
    
- Fügt ein Objekt **RTCPropertySet** vom Typ **ControlAccessRight** unter **Extended-Rights** , das auf die Benutzer- und kontaktklassen angewendet.
    
- Fügt ein Objekt **RTCUserSearchPropertySet** vom Typ **ControlAccessRight** unter **Extended-Rights** , das auf Benutzer-, Kontakt-, Organisationseinheit und DomainDNS-Klassen angewendet wird.
    
- **MsRTCSIP-PrimaryUserAddress** unter Attributs **ExtraColumns** der jede Sprache Organisationseinheit (OU) Anzeigebezeichner fügt (beispielsweise CN = OrganizationalUnit-Display, CN = 409,CN = DisplaySpecifiers) und die Werte der kopiert die dem Attribut **ExtraColumns** der Standardanzeige (z. B. CN = Default-Display, CN = 409,CN = DisplaySpecifiers).
    
- Hinzufügt, dass **MsRTCSIP-PrimaryUserAddress**, **MsRTCSIP-PrimaryHomeServer**und **MsRTCSIP-UserEnabled** Filtern Attribute unter Attributs **AttributeDisplayNames** für jede Sprache Bezeichner für Benutzer, Kontakte angezeigt, und InetOrgPerson-Objekte (in Englisch z. B.: CN = User-Display, CN = 409,CN = DisplaySpecifiers).
    

