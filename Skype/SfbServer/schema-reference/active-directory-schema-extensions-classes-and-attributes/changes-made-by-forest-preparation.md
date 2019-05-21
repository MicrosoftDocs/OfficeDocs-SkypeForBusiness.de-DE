---
title: Änderungen, die von der Gesamtstrukturvorbereitung in Skype for Business Server vorgenommen wurden
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
description: In diesem Abschnitt werden die globalen Einstellungen und Objekte sowie die Gruppen "Universeller Dienst" und "Verwaltung" beschrieben, die vom Gesamtstrukturvorbereitungsschritt erstellt werden.
ms.openlocfilehash: ece4a9bd1db5f43b52a96265dee41ee3a0a30b22
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296700"
---
# <a name="changes-made-by-forest-preparation-in-skype-for-business-server"></a>Änderungen, die von der Gesamtstrukturvorbereitung in Skype for Business Server vorgenommen wurden

In diesem Abschnitt werden die globalen Einstellungen und Objekte sowie die Gruppen "Universeller Dienst" und "Verwaltung" beschrieben, die vom Gesamtstrukturvorbereitungsschritt erstellt werden.

## <a name="active-directory-global-settings-and-objects"></a>Globale Active Directory-Einstellungen und-Objekte

Wenn Sie globale Einstellungen im Konfigurationscontainer speichern (wie dies bei allen neuen Skype for Business Server-Bereitstellungen der Fall ist), verwendet die Gesamtstrukturvorbereitung den vorhandenen Dienste-Container und fügt unter dem Konfiguration\Dienste ein **RTC-Dienst** Objekt hinzu. Objekt. Unter dem RTC-Dienstobjekt fügt die Gesamtstrukturvorbereitung ein **globales Einstellungs** Objekt vom Typ Attribut msRTCSIP-Global Container hinzu. Das Global Settings-Objekt enthält alle Einstellungen, die für die Bereitstellung von Skype for Business Server gelten. Wenn Sie globale Einstellungen im Systemcontainer speichern, verwendet die Gesamtstrukturvorbereitung einen Microsoft-Container unter dem Stammdomänen System Container und ein RTC-Dienstobjekt unter dem System\Microsoft-Objekt.

Bei der Gesamtstrukturvorbereitung wird auch ein neues **Attribut msRTCSIP-Domänen** Objekt für die Stammdomäne hinzugefügt, in der die Prozedur ausgeführt wird.

## <a name="active-directory-universal-service-and-administration-groups"></a>Active Directory-universelle Dienst-und Verwaltungsgruppen

Bei der Gesamtstrukturvorbereitung werden universelle Gruppen basierend auf der von Ihnen angegebenen Domäne erstellt und für diese Gruppen Zugriffssteuerungseinträge (ACEs) hinzugefügt. In diesem Schritt werden die universellen Gruppen in den Benutzer Containern der Domäne erstellt, die Sie angeben.

Universelle Gruppen ermöglichen Administratoren den Zugriff auf und die Verwaltung globaler Einstellungen und Dienste. Bei der Gesamtstrukturvorbereitung werden die folgenden Typen von universellen Gruppen hinzugefügt:

- **Administrative Gruppen** Diese Gruppen definieren Administratorrollen für ein Skype for Business Server-Netzwerk.

- **Infrastrukturgruppen** Diese Gruppen bieten die Berechtigung für den Zugriff auf bestimmte Bereiche der Skype for Business Server-Infrastruktur. Sie funktionieren als Komponenten administrativer Gruppen. Sie sollten diese Gruppen nicht ändern oder Benutzer direkt hinzufügen.

- **Dienstgruppen** Diese Gruppen sind Dienstkonten, die für den Zugriff auf verschiedene Skype for Business Server-Dienste erforderlich sind.

In der folgenden Tabelle werden die administrativen Gruppen beschrieben.

**Während der Gesamtstrukturvorbereitung erstellte administrative Gruppen**

|**Administrative Gruppe**|**Beschreibung**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> |Ermöglicht Mitgliedern das Verwalten von Server-und Pooleinstellungen, einschließlich aller Serverrollen, globalen Einstellungen und Benutzer.  <br/> |
|RTCUniversalUserAdmins  <br/> |Ermöglicht Mitgliedern, Benutzereinstellungen zu verwalten und Benutzer von einem Server oder Pool in einen anderen zu verschieben.  <br/> |
|RTCUniversalReadOnlyAdmins  <br/> |Ermöglicht Mitgliedern, Server-, Pool-und Benutzereinstellungen zu lesen.  <br/> |

In der folgenden Tabelle werden die Infrastrukturgruppen beschrieben.

**Während der Gesamtstrukturvorbereitung erstellte Infrastrukturgruppen**

|**Infrastrukturgruppe**|**Beschreibung**|
|:-----|:-----|
|RTCUniversalGlobalWriteGroup  <br/> |Gewährt Schreibzugriff auf globale Einstellungsobjekte für Skype for Business Server.  <br/> |
|RTCUniversalGlobalReadOnlyGroup  <br/> |Gewährt schreibgeschützten Zugriff auf globale Einstellungsobjekte für Skype for Business Server.  <br/> |
|RTCUniversalUserReadOnlyGroup hinzugefügt  <br/> |Gewährt schreibgeschützten Zugriff auf die Benutzereinstellungen von Skype for Business Server.  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Gewährt schreibgeschützten Zugriff auf Skype for Business Server-Einstellungen. Diese Gruppe hat keinen Zugriff auf Einstellungen auf Poolebene, sondern nur auf Einstellungen, die für einen einzelnen Server spezifisch sind.  <br/> |
|RTCUniversalSBATechnicians  <br/> |Gewährt schreibgeschützten Zugriff auf die Konfiguration von Skype for Business Server und wird während der Installation in der lokalen Gruppe Administratoren der Überlebenden Branch-Appliances gespeichert.  <br/> |

In der folgenden Tabelle werden die Dienstgruppen beschrieben.

**Während der Gesamtstrukturvorbereitung erstellte Dienstgruppen**

|**Dienstgruppe**|**Beschreibung**|
|:-----|:-----|
|RTCHSUniversalServices  <br/> |Enthält Dienstkonten, mit denen Front-End-Server und Standard Edition-Server ausgeführt werden. Diese Gruppe ermöglicht Servern Lese-und Schreibzugriff auf die globalen Einstellungen und Active Directory-Benutzerobjekte von Skype for Business Server.  <br/> |
|RTCComponentUniversalServices  <br/> |Enthält Dienstkonten, die für die Ausführung von A/V-Konferenzservern, Webdiensten, Mediations Servern, Archivierungsservern und Überwachungs Servern verwendet werden.  <br/> |
|RTCProxyUniversalServices  <br/> |Enthält Dienstkonten, die für die Ausführung von Skype for Business Server Edge-Servern verwendet werden.  <br/> |
|RTCUniversalConfigReplicator  <br/> |Umfasst Server, die an der Replikation des zentralen Verwaltungsspeichers von Skype for Business Server teilnehmen können.  <br/> |
|RTCSBAUniversalServices  <br/> |Gewährt schreibgeschützten Zugriff auf Skype for Business Server-Einstellungen, ermöglicht aber die Konfiguration für die Installation eines überlebensfähigen Branch-Servers und die Bereitstellung von Survivable Branch Appliances.  <br/> |

Die Gesamtstrukturvorbereitung fügt dann den entsprechenden Infrastrukturgruppen Dienst-und Verwaltungsgruppen wie folgt hinzu:

- RTCUniversalServerAdmins wird zu RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup und RTCUniversalUserReadOnlyGroup hinzugefügt hinzugefügt.

- RTCUniversalUserAdmins wird als Mitglied von RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup und RTCUniversalUserReadOnlyGroup hinzugefügt hinzugefügt.

- RTCHSUniversalServices, RTCComponentUniversalServices und RTCUniversalReadOnlyAdmins werden als Mitglieder von RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup und RTCUniversalUserReadOnlyGroup hinzugefügt hinzugefügt.

Bei der Gesamtstrukturvorbereitung werden auch die folgenden rollenbasierten Zugriffssteuerungsgruppen erstellt:

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

Details zu den Rollen und den jeweils zulässigen Aufgaben finden Sie unter [rollenbasierte Zugriffssteuerung](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) in der Planungsdokumentation.

Bei der Gesamtstrukturvorbereitung werden sowohl private als auch öffentliche ACEs erstellt. Sie erstellt private ACEs auf dem Container für globale Einstellungen, der von Skype for Business Server verwendet wird. Dieser Container wird nur von Skype for Business Server verwendet und befindet sich entweder im Konfigurationscontainer oder im System Container in der Stammdomäne, je nachdem, wo Sie die globalen Einstellungen speichern. Die von der Gesamtstrukturvorbereitung erstellten öffentlichen ACEs sind in der folgenden Tabelle aufgelistet.

**Von der Gesamtstrukturvorbereitung erstellte öffentliche ACEs**


| **ACE**                                                                 | **RTCUniversalGlobalReadOnlyGroup** |
|:------------------------------------------------------------------------|:------------------------------------|
| Read Root Domain System Container (nicht geerbt)**\\**\* <br/>        | X  <br/>                            |
| Lesen des DisplaySpecifiers-Containers der Konfiguration (nicht geerbt)  <br/> | X  <br/>                            |

> [!NOTE]
> <strong>\\</strong>* Nicht geerbte ACEs gewähren unter diesen Containern keinen Zugriff auf untergeordnete Objekte. ACEs, die geerbt werden, gewähren Zugriff auf untergeordnete Objekte unter diesen Containern.

Im Konfigurationscontainer führt die Gesamtstrukturvorbereitung unter dem Konfigurationsnamenskontext die folgenden Aufgaben aus:

- Fügt einen Eintrag **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** für die **RTC-Eigenschaften** Seite unter den Attributen adminContextMenu und adminPropertyPages des Sprachanzeige Bezeichners für Benutzer, Kontakte und inetOrgPerson hinzu (beispielsweise CN = Benutzeranzeige, CN = 409, CN = DisplaySpecifiers).

- Fügt unter **Erweiterte Rechte** , die für die Benutzer-und Kontaktklassen gelten, ein **RTCPropertySet** -Objekt vom Typ **controlAccessRight** hinzu.

- Fügt unter **Erweiterte Rechte** , die für Benutzer-, Kontakt-, ou-und domainDNS-Klassen gelten, ein **RTCUserSearchPropertySet** -Objekt vom Typ **controlAccessRight** hinzu.

- Fügt **Attribut msRTCSIP-PrimaryUserAddress** unter dem **extraColumns** -Attribut des jeweiligen Anzeigebezeichners der sprach Organisationseinheit (z. b. CN = organizationalUnit-Display, CN = 409, CN = DisplaySpecifiers) hinzu und kopiert die Werte der **extraColumns** -Attribut der Standardanzeige (beispielsweise CN = default-Display, CN = 409, CN = DisplaySpecifiers).

- Fügt **Attribut msRTCSIP-PrimaryUserAddress**-, **Attribut msRTCSIP-PrimaryHomeServer**-und **Attribut msRTCSIP-UserEnabled-** Filterattribute unter dem **attributeDisplayNames** -Attribut jedes Sprachanzeige Bezeichners für Benutzer, Kontakte, und InetOrgPerson-Objekte (beispielsweise in Englisch: CN = User-Display, CN = 409, CN = DisplaySpecifiers).


