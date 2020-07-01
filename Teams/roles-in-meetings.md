---
title: Funktionen für Referenten und Teilnehmer in Microsoft Teams-Besprechungen
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: dansteve
search.appverid: MET150
f1.keywords:
- NOCSH
description: Erfahren Sie mehr über die Funktionen für Referenten und Teilnehmer in Microsoft Teams-Besprechungen.
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: b0302a5c1f09e6ed6bfbb877709ed3562ce1440a
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938174"
---
<a name="presenter-and-participant-capabilities-in-a-teams-meeting"></a>Funktionen für Referenten und Teilnehmer in Microsoft Teams-Besprechungen
======================================================

Microsoft Teams-Besprechungen unterstützen viele Teilnehmertypen. Die Teilnehmer können basierend auf ihren Rollen innerhalb bzw. außerhalb einer Organisation auf verschiedene Besprechungsfeatures zugreifen.

Nachfolgend die verfügbaren Besprechungsfeatures:

- Chat (umfasst Fotos und Aufkleber)
- Besprechungsnotizen
- Whiteboard
- Aufzeichnung läuft
- Dateien
    - Freigeben einer Datei in einem Besprechungs-Chat und anzeigen/herunterladen einer Datei aus einem Besprechungs-Chat
    - Eine PPT-Präsentation in einer Besprechung (nicht über Screensharing) zeigen und eine PPT-Präsentation in einer Besprechung ansehen
- Besprechungen planen (nur für Besprechungen)

In diesem Artikel werden die Funktionen für Teilnehmer beschrieben und erläutert, auf welche Besprechungsfeatures sie Zugriff haben.

## <a name="presenters-and-organizers"></a>Referenten und Organisatoren

Referenten und Organisatoren umfassen:

- Referenten aus meiner Organisation
- Referenten aus anderen Organisationen (einschließlich anonyme und externe Teilnehmer). Referenten werden vom Organisator bestimmt und brauchen eine persönliche Einladung von diesem.

Referenten und Organisatoren haben Zugriff auf alle Features in einer Besprechung oder einem Live-Ereignis.

## <a name="participants"></a>Teilnehmer

Es gibt verschiedene Arten von Besprechungsteilnehmern:

- [Mandanteninterne Teilnehmer](#in-tenant-participant)
- [Gastteilnehmer](#guest-participant)
- [Externe Teilnehmer (Partner)](#external-federated-participant)
- [Anonyme Teilnehmer](#anonymous-participant)

### <a name="in-tenant-participant"></a>Mandanteninterne Teilnehmer

Ein mandanteninterner Teilnehmer gehört zur Organisation und verfügt über Anmeldeinformationen für den Mandanten. Erfahren Sie mehr über diesen Teilnehmertyp unter [Sicherheit und Microsoft Teams](teams-security-guide.md#participant-types).

|  |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **Feature**        | Vor der Besprechung | Während der Besprechung | Nach der Besprechung |
| Chat | Ja | Ja | Ja |
| Besprechungsnotizen | Ja | Ja |Ja |
| Whiteboard | Ja | Ja |Ja |
| Aufzeichnung läuft | Nicht zutreffend |Ja | Ja |
| Dateien: Freigeben einer Datei in einem Besprechungs-Chat und anzeigen/herunterladen einer Datei aus einem Besprechungs-Chat | Ja | Ja | Ja |
| Dateien: Eine PPT-Präsentation in einer Besprechung (nicht über Screensharing) zeigen und eine PPT-Präsentation in einer Besprechung ansehen | Ja | Ja | Ja |
| Besprechungen planen | Ja | Nicht zutreffend | Nicht zutreffend |
|||||||

### <a name="guest-participant"></a>Gastteilnehmer

Ein Gastteilnehmer ist jemand aus einer anderen Organisation, der basierend auf der Azure Active Directory-B2B-Plattform zum Zugriff auf Microsoft Teams oder andere Ressourcen im Mandanten Ihrer Organisation eingeladen wurde. Gastbenutzer können zu herkömmlichen Besprechungen und Kanalbesprechungen eingeladen werden. Erfahren Sie mehr über Gastteilnehmer unter [Ablauf für Gäste](guest-experience.md#comparison-of-team-member-and-guest-capabilities).

|  |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **Feature**        | Vor der Besprechung | Während der Besprechung | Nach der Besprechung |
| Chat | Ja | Ja | Ja |
| Besprechungsnotizen | Ja | Ja | Ja |
| Whiteboard | Nein | Nein |Nein |
| Aufzeichnung läuft | Nicht zutreffend |Nein | Nein |
| Dateien: Freigeben einer Datei in einem Besprechungs-Chat und anzeigen/herunterladen einer Datei aus einem Besprechungs-Chat | Ja | Ja | Ja |
| Dateien: Eine PPT-Präsentation in einer Besprechung (nicht über Screensharing) zeigen und eine PPT-Präsentation in einer Besprechung ansehen | Ja | Ja | Ja |
| Besprechungen planen | Nein | – | Nicht zutreffend |
|||||||

### <a name="external-federated-participant"></a>Externe Teilnehmer (Partner)

Bei einem externen Teilnehmer handelt es sich um eine Person, die Microsoft Teams in einer anderen Organisation verwendet und zur Teilnahme an einer Besprechung eingeladen wurde, jedoch keinen Zugriff auf andere freigegebene Ressourcen Ihrer Organisation hat. Externe Teilnehmer werden in der Besprechungsliste mit dem gleichen Identitätsnamen wie in ihrer eigenen Organisation angezeigt. Weitere Informationen zu externen Teilnehmern erhalten Sie unter [Kommunikation mit Benutzern aus anderen Organisationen](communicate-with-users-from-other-organizations.md#external-access).

|  ||
|-|-|-|
| **Feature** |||
| Chat | Ja |
| Besprechungsnotizen | Nicht zutreffend |  
| Whiteboard | Nicht zutreffend |
| Aufzeichnung läuft | – |  
| Dateien: Freigeben einer Datei in einem Besprechungs-Chat und anzeigen/herunterladen einer Datei aus einem Besprechungs-Chat |  |  |  |
| Dateien: Eine PPT-Präsentation in einer Besprechung (nicht über Screensharing) zeigen und eine PPT-Präsentation in einer Besprechung ansehen |  |  |  |
| Besprechungen planen | Nicht zutreffend |
|||

### <a name="anonymous-participant"></a>Anonyme Teilnehmer

Ein anonymer Teilnehmer ist wie ein externer Benutzer, seine Identität wird jedoch nicht in der Besprechung angezeigt. Zum Zeitpunkt des Beitritts gibt er manuell einen Nickname ein. Mehr über anonyme Teilnehmer erfahren Sie unter [Sicherheit und Microsoft Teams](teams-security-guide.md#participant-types).

|   | | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **Feature**        | Vor der Besprechung | Während der Besprechung | Nach der Besprechung |
| Chat | Nicht zutreffend | Ja | Nicht zutreffend |
| Besprechungsnotizen | Nicht zutreffend | Nein | Nicht zutreffend |
| Whiteboard | Nicht zutreffend | Nein | Nicht zutreffend |
| Aufzeichnung läuft | Nicht zutreffend | Nein | – |
| Dateien: Freigeben einer Datei in einem Besprechungs-Chat und anzeigen/herunterladen einer Datei aus einem Besprechungs-Chat |  |  |  |
| Dateien: Eine PPT-Präsentation in einer Besprechung (nicht über Screensharing) zeigen und eine PPT-Präsentation in einer Besprechung ansehen |  |  |  |
| Besprechungen planen | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend |
|||||||

## <a name="related-topics"></a>Verwandte Themen

[Sicherheit und Microsoft Teams](teams-security-guide.md)

[Gastzugriff in Teams](guest-access.md)
