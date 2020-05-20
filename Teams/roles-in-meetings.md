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
ms.openlocfilehash: 11c5858532ade4fd4ed00f7c8f6d1d0c94baeb2d
ms.sourcegitcommit: 1a6b4efad1e6a958cdbaae4b0e2e231145c9658f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "44321734"
---
<a name="presenter-and-participant-capabilities-in-a-teams-meeting"></a>Funktionen für Referenten und Teilnehmer in Microsoft Teams-Besprechungen
======================================================

Microsoft Teams-Besprechungen unterstützen viele Teilnehmertypen. Die Teilnehmer können basierend auf ihren Rollen innerhalb bzw. außerhalb einer Organisation auf verschiedene Besprechungsfeatures zugreifen.

Nachfolgend die verfügbaren Besprechungsfeatures:

- Chat (umfasst Fotos und Aufkleber)
- Besprechungsnotizen
- Whiteboard
- Aufzeichnen
- Dateien
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

|Besprechung  |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **Feature**        | Vor der Besprechung | Während der Besprechung | Nach der Besprechung |
| Chat | Ja | Ja | Ja |
| Besprechungsnotizen | Ja | Ja |Ja |
| Whiteboard | Ja | Ja |Ja |
| Aufzeichnen | Nicht zutreffend |Ja | Ja |
| Dateien | Ja | Ja | Ja |
| Besprechungen planen | Ja | Nicht zutreffend | Nicht zutreffend |
|||||||

### <a name="guest-participant"></a>Gastteilnehmer

Ein Gastteilnehmer ist jemand aus einer anderen Organisation, der basierend auf der Azure Active Directory-B2B-Plattform zum Zugriff auf Microsoft Teams oder andere Ressourcen im Mandanten Ihrer Organisation eingeladen wurde. Gastbenutzer können zu herkömmlichen Besprechungen und Kanalbesprechungen eingeladen werden. Erfahren Sie mehr über Gastteilnehmer unter [Ablauf für Gäste](guest-experience.md#comparison-of-team-member-and-guest-capabilities).

| Besprechung |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **Feature**        | Vor der Besprechung | Während der Besprechung | Nach der Besprechung |
| Chat | Ja | Ja | Ja |
| Besprechungsnotizen | Ja | Ja | Ja |
| Whiteboard | Nein | Nein |Nein |
| Aufzeichnen | Nicht zutreffend |Nein | Nein |
| Dateien | Ja | Ja | Ja |
| Besprechungen planen | Nein | – | Nicht zutreffend |
|||||||

### <a name="external-federated-participant"></a>Externe Teilnehmer (Partner)

Bei einem externen Teilnehmer handelt es sich um eine Person, die Microsoft Teams in einer anderen Organisation verwendet und zur Teilnahme an einer Besprechung eingeladen wurde, jedoch keinen Zugriff auf andere freigegebene Ressourcen Ihrer Organisation hat. Externe Teilnehmer werden in der Besprechungsliste mit dem gleichen Identitätsnamen wie in ihrer eigenen Organisation angezeigt. Weitere Informationen zu externen Teilnehmern erhalten Sie unter [Kommunikation mit Benutzern aus anderen Organisationen](communicate-with-users-from-other-organizations.md#external-access).

| Besprechung (kann einem Team nur als Gast hinzugefügt werden) ||
|-|-|-|
| **Feature** |||
| Chat | Nicht zutreffend |
| Besprechungsnotizen | Nicht zutreffend |  
| Whiteboard | Nicht zutreffend |
| Aufzeichnen | Nicht zutreffend |  
| Dateien | Nicht zutreffend |
| Besprechungen planen | Nicht zutreffend |
|||

### <a name="anonymous-participant"></a>Anonyme Teilnehmer

Ein anonymer Teilnehmer ist wie ein externer Benutzer, seine Identität wird jedoch nicht in der Besprechung angezeigt. Zum Zeitpunkt des Beitritts gibt er manuell einen Nickname ein. Mehr über anonyme Teilnehmer erfahren Sie unter [Sicherheit und Microsoft Teams](teams-security-guide.md#participant-types).

| Besprechung  | | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **Feature**        | Vor der Besprechung | Während der Besprechung | Nach der Besprechung |
| Chat | Nicht zutreffend | Nein | Nicht zutreffend |
| Besprechungsnotizen | Nicht zutreffend | Nein | Nicht zutreffend |
| Whiteboard | Nicht zutreffend | Nein | Nicht zutreffend |
| Aufzeichnen | Nicht zutreffend | Nein | Nicht zutreffend |
| Dateien | Nicht zutreffend | Nein | Nicht zutreffend |
| Besprechungen planen | Nicht zutreffend | N/V | Nicht zutreffend |
|||||||

## <a name="related-topics"></a>Verwandte Themen

[Sicherheit und Microsoft Teams](teams-security-guide.md)

[Gastzugriff in Teams](guest-access.md)
