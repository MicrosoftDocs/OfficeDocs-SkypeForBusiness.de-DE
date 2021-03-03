---
title: Änderungen, die bei der Gesamtstrukturvorbereitung in Skype for Business Server vorgenommen wurden
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
description: Dieser Abschnitt enthält eine Beschreibung der globalen Einstellungen und Objekte und der universellen Dienst- und Verwaltungsgruppen, die bei der Gesamtstrukturvorbereitung erstellt werden.
ms.openlocfilehash: 4e8032cb91b012c710dc509708a813d55825f7a2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831915"
---
# <a name="changes-made-by-forest-preparation-in-skype-for-business-server"></a>Änderungen, die bei der Gesamtstrukturvorbereitung in Skype for Business Server vorgenommen wurden

Dieser Abschnitt enthält eine Beschreibung der globalen Einstellungen und Objekte und der universellen Dienst- und Verwaltungsgruppen, die bei der Gesamtstrukturvorbereitung erstellt werden.

## <a name="active-directory-global-settings-and-objects"></a>Globale Einstellungen und Objekte in Active Directory

Wenn Sie globale Einstellungen im Konfigurationscontainer speichern (wie dies bei allen neuen Skype for Business Server-Bereitstellungen der Fall ist), verwendet die Gesamtstrukturvorbereitung den vorhandenen Dienstcontainer und fügt unter dem Objekt Configuration\Services ein Objekt des **RtC Service** hinzu. Unterhalb des Objekts "RTC Service" wird bei der Gesamtstrukturvorbereitung ein Objekt **Global Settings** vom Typ "msRTCSIP-GlobalContainer" hinzugefügt. Das globale Einstellungsobjekt enthält alle Einstellungen, die für die Skype for Business Server-Bereitstellung gelten. Wenn Sie die globalen Einstellungen im Systemcontainer speichern, wird bei der Gesamtstrukturvorbereitung ein Microsoft-Container unterhalb des Systemcontainers der Stammdomäne verwendet und unterhalb des Objekts "System\Microsoft" ein Objekt "RTC Service" hinzugefügt.

Außerdem wird während der Gesamtstrukturvorbereitung ein neues Objekt **msRTCSIP-Domain** für die Stammdomäne hinzugefügt, in der das Verfahren ausgeführt wird.

## <a name="active-directory-universal-service-and-administration-groups"></a>Universelle Dienst- und Verwaltungsgruppen in Active Directory

Die Gesamtstrukturvorbereitung erstellt universelle Gruppen anhand der von Ihnen angegebenen Domäne und fügt Zugriffssteuerungseinträge (Access Control Entries, ACEs) für diese Gruppen hinzu. In diesem Schritt werden die universellen Gruppen in den Benutzercontainern der Domäne erstellt, die Sie angegeben haben.

Anhand von universellen Gruppen können Administratoren globale Einstellungen und Dienste verwenden und verwalten. Bei der Gesamtstrukturvorbereitung werden die folgenden Typen von universellen Gruppen hinzugefügt:

- **Administrative Gruppen** Diese Gruppen definieren Administratorrollen für ein Skype for Business Server-Netzwerk.

- **Infrastrukturgruppen** Diese Gruppen bieten die Berechtigung für den Zugriff auf bestimmte Bereiche der Skype for Business Server-Infrastruktur. Sie fungieren als Komponenten von administrativen Gruppen. Sie sollten diese Gruppen weder ändern noch direkt Benutzer zu ihnen hinzufügen.

- **Dienstgruppen** Diese Gruppen sind Dienstkonten, die für den Zugriff auf verschiedene Skype for Business Server-Dienste erforderlich sind.

In der folgenden Tabelle werden die administrativen Gruppen beschrieben.

**Administrative Gruppen, die während der Gesamtstrukturvorbereitung erstellt werden**

|**Administrative Gruppe**|**Beschreibung**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> |Erlaubt den Mitgliedern, Server- und Pooleinstellungen zu verwalten, darunter alle Serverrollen, globalen Einstellungen und Benutzer.  <br/> |
|RTCUniversalUserAdmins  <br/> |Ermöglicht Mitgliedern das Verwalten von Benutzereinstellungen und das Verschieben von Benutzern von einem Server oder Pool zu einem anderen.  <br/> |
|RTCUniversalReadOnlyAdmins  <br/> |Ermöglicht Mitgliedern das Lesen von Server-, Pool- und Benutzereinstellungen.  <br/> |

In der folgenden Tabelle werden die Infrastrukturgruppen beschrieben.

**Infrastrukturgruppen, die während der Gesamtstrukturvorbereitung erstellt werden**

|**Infrastrukturgruppe**|**Beschreibung**|
|:-----|:-----|
|RTCUniversalGlobalWriteGroup  <br/> |Gewährt Schreibzugriff auf globale Einstellungsobjekte für Skype for Business Server.  <br/> |
|RTCUniversalGlobalReadOnlyGroup  <br/> |Gewährt schreibgeschützten Zugriff auf globale Einstellungsobjekte für Skype for Business Server.  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Gewährt schreibgeschützten Zugriff auf Skype for Business Server-Benutzereinstellungen.  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Gewährt schreibgeschützten Zugriff auf Skype for Business Server-Einstellungen. Diese Gruppe hat keinen Zugriff auf die Einstellungen auf Poolebene, sondern lediglich auf Einstellungen für einzelne Server.  <br/> |
|RTCUniversalSBATechnicians  <br/> |Gewährt schreibgeschützten Zugriff auf die Skype for Business Server-Konfiguration und wird während der Installation in der Lokalen Administratorgruppe der Survivable Branch Appliances platziert.  <br/> |

In der folgenden Tabelle werden die Dienstgruppen beschrieben.

**Dienstgruppen, die während der Gesamtstrukturvorbereitung erstellt werden**

|**Dienstgruppe**|**Beschreibung**|
|:-----|:-----|
|RTCHSUniversalServices  <br/> |Enthält Dienstkonten, die zum Ausführen von Front-End-Server- und Standard Edition-Servern verwendet werden. Diese Gruppe ermöglicht Servern Lese-/Schreibzugriff auf globale Skype for Business Server-Einstellungen und Active Directory-Benutzerobjekte.  <br/> |
|RTCComponentUniversalServices  <br/> |Umfasst Dienstkonten zum Ausführen von A/V-Konferenzservern, Webdiensten, Vermittlungsservern, Archivierungsservern und Monitoring Server.  <br/> |
|RTCProxyUniversalServices  <br/> |Umfasst Dienstkonten, die zum Ausführen von Skype for Business Server-Edgeservern verwendet werden.  <br/> |
|RTCUniversalConfigReplicator  <br/> |Enthält Server, die an der Replikation des zentralen Verwaltungsspeichers von Skype for Business Server teilnehmen können.  <br/> |
|RTCSBAUniversalServices  <br/> |Gewährt schreibgeschützten Zugriff auf Skype for Business Server-Einstellungen, ermöglicht jedoch die Konfiguration für die Installation eines Survivable Branch Servers und einer Survivable Branch Appliance-Bereitstellung.  <br/> |

Die Gesamtstrukturvorbereitung fügt den entsprechenden Infrastrukturgruppen dann wie folgt Dienst- und Verwaltungsgruppen hinzu:

- "RTCUniversalServerAdmins" wird zu "RTCUniversalGlobalReadOnlyGroup", "RTCUniversalGlobalWriteGroup", "RTCUniversalServerReadOnlyGroup" und "RTCUniversalUserReadOnlyGroup" hinzugefügt.

- "RTCUniversalUserAdmins" wird als Mitglied von "RTCUniversalGlobalReadOnlyGroup", "RTCUniversalServerReadOnlyGroup" und "RTCUniversalUserReadOnlyGroup" hinzugefügt.

- "RTCHSUniversalServices", "RTCComponentUniversalServices" und "RTCUniversalReadOnlyAdmins" werden als Mitglieder von "RTCUniversalGlobalReadOnlyGroup", "RTCUniversalServerReadOnlyGroup" und "RTCUniversalUserReadOnlyGroup" hinzugefügt.

Bei der Gesamtstrukturvorbereitung werden außerdem die folgenden rollenbasierten Zugriffssteuerungsgruppen erstellt:

- CSAdministrator

- CSArchivingAdministrator

- CSHelpDesk

- CSLocationAdministrator

- CSResponseGroupAdministrator

- CSServerAdministrator

- CSUserAdministrator

- CSViewOnlyAdministrator

- CSVoiceAdministrator

- CsPersistentChatAdministator

- CsResponseGroupManager

Ausführliche Informationen zu rollenbasierten Zugriffssteuerungsrollen und den Aufgaben, die mit jeder dieser Rollen ausgeführt werden können, finden Sie unter [Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) in der Planungsdokumentation.

Bei der Gesamtstrukturvorbereitung werden sowohl private als auch öffentliche ACEs erstellt. Es erstellt private ACEs für den globalen Einstellungscontainer, der von Skype for Business Server verwendet wird. Dieser Container wird nur von Skype for Business Server verwendet und befindet sich entweder im Konfigurationscontainer oder im Systemcontainer in der Stammdomäne, je nachdem, wo Sie die globalen Einstellungen speichern. Die von der Gesamtstrukturvorbereitung erstellten öffentlichen ACEs sind in der folgenden Tabelle aufgeführt.

**Von der Gesamtstruktur erstellte öffentliche ACEs**


| **ACE**                                                                 | **RTCUniversalGlobalReadOnlyGroup** |
|:------------------------------------------------------------------------|:------------------------------------|
| Systemcontainer der Stammdomäne lesen (nicht geerbt) **\\**\* <br/>        | X  <br/>                            |
| Read Configuration's DisplaySpecifiers container (not inherited)  <br/> | X  <br/>                            |

> [!NOTE]
> <strong>\\</strong>*ACEs, die nicht geerbt werden, gewähren keinen Zugriff auf untergeordnete Objekte unter diesen Containern. ACEs, die vererbt werden, gewähren Zugriff auf untergeordnete Objekte im betreffenden Container.

Die Gesamtstrukturvorbereitung führt die folgenden Aufgaben im Konfigurationscontainer unter dem Namenskontext für die Konfiguration durch:

- Hinzufügen eines Eintrags **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** für die Seite **RTC property** unter den Attributen "adminContextMenu" und "adminPropertyPages" des Anzeigebezeichners für Sprachen für Benutzer, Kontakte und InetOrgPersons (z. B.: CN=user-Display,CN=409,CN=DisplaySpecifiers)

- Hinzufügen eines Objekts **RTCPropertySet** vom Typ **controlAccessRight** unterhalb von **Extended-Rights**, das auf die User- und Contact-Klassen angewendet wird

- Hinzufügen eines Objekts **RTCUserSearchPropertySet** vom Typ **controlAccessRight** unterhalb von **Extended-Rights**, das auf die User-, Contact-, OU- und DomainDNS-Klassen angewendet wird

- Hinzufügen von **msRTCSIP-PrimaryUserAddress** unter dem Attribut **extraColumns** der jeweiligen Anzeigebezeichner für die Sprachen der Organisationseinheit (z. B.: CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) und Kopieren der Werte des Attributs **extraColumns** der Standardanzeige (z. B.: CN=default-Display, CN=409,CN=DisplaySpecifiers)

- Hinzufügen der Filterattribute **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer** und **msRTCSIP-UserEnabled** unterhalb des Attributs **attributeDisplayNames** der jeweiligen Anzeigebezeichners für Sprachen für Benutzer-, Kontakt- und InetOrgPerson-Objekte (z. B. auf Englisch: CN=user-Display,CN=409,CN=DisplaySpecifiers)


