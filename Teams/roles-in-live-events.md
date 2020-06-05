---
title: Funktionen für Referenten und Teilnehmer in Teams-Live-Ereignissen
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
description: Erfahren Sie mehr über die Funktionen für Referenten und Teilnehmer in Teams-Live-Ereignissen.
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: 7714442be770420797df1c51a532f769eb0350a4
ms.sourcegitcommit: f9db7effbb1e56484686afe4724cc3b73380166d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "44565858"
---
<a name="presenter-and-participant-capabilities-in-a-teams-live-event"></a>Funktionen für Referenten und Teilnehmer in Teams-Live-Ereignissen
======================================================

Microsoft Teams-Live-Ereignisse unterstützen viele Teilnehmertypen. Die Teilnehmer können basierend auf ihren Rollen innerhalb bzw. außerhalb einer Organisation auf verschiedene Live-Ereignis-Features zugreifen.

Nachfolgend die verfügbaren Besprechungsfeatures:

- Chat (umfasst Fotos und Aufkleber)
- Besprechungsnotizen
- Whiteboard
- Aufzeichnung läuft
- Dateien

In diesem Artikel werden die Funktionen für Teilnehmer beschrieben und erläutert, auf welche Live-Ereignis-Features sie Zugriff haben.

## <a name="presenters-and-organizers"></a>Referenten und Organisatoren

Referenten und Organisatoren umfassen:

- Referenten aus meiner Organisation
- Referenten aus anderen Organisationen. Referenten werden vom Organisator bestimmt und brauchen eine persönliche Einladung von diesem.

Referenten und Organisatoren haben Zugriff auf alle Features in einem Live-Ereignis.

## <a name="participants"></a>Teilnehmer

Es gibt verschiedene Arten von Live-Ereignis-Teilnehmern:

- [Mandanteninterne Teilnehmer](#in-tenant-participant)
- [Gastteilnehmer](#guest-participant)
- [Externe Teilnehmer (Partner)](#external-federated-participant)
- [Anonyme Teilnehmer](#anonymous-participant)

### <a name="in-tenant-participant"></a>Mandanteninterne Teilnehmer

Ein mandanteninterner Teilnehmer gehört zur Organisation und verfügt über Anmeldeinformationen für den Mandanten. Erfahren Sie mehr über diesen Teilnehmertyp unter [Sicherheit und Microsoft Teams](teams-security-guide.md#participant-types).

| Live-Ereignis |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
|  **Feature**       | Vor der Besprechung | Während der Besprechung | Nach der Besprechung |
| Chat | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend |
| Besprechungsnotizen | Ja | Ja |Ja |
| Whiteboard | Ja | Ja |Ja |
| Aufzeichnung läuft | Nicht zutreffend |Ja | Ja |
| Dateien | Ja | Ja | Ja |
|||||||


### <a name="guest-participant"></a>Gastteilnehmer

Ein Gastteilnehmer ist jemand aus einer anderen Organisation, der basierend auf der Azure Active Directory-B2B-Plattform zum Zugriff auf Microsoft Teams oder andere Ressourcen im Mandanten Ihrer Organisation eingeladen wurde. Gastbenutzer können zu herkömmlichen Besprechungen und Kanalbesprechungen eingeladen werden. Erfahren Sie mehr über Gastteilnehmer unter [Ablauf für Gäste](guest-experience.md#comparison-of-team-member-and-guest-capabilities).

| Live-Ereignis  | | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **Feature**        | Vor der Besprechung | Während der Besprechung | Nach der Besprechung |
| Chat | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend |
| Besprechungsnotizen | Ja | Ja | Ja |
| Whiteboard | Nein | Nein | Nein |
| Aufzeichnung läuft | Nicht zutreffend | Nein | Nein |
| Dateien | Nein | Nein | Nein |
|||||||


### <a name="external-federated-participant"></a>Externe Teilnehmer (Partner)

Bei einem externen Teilnehmer handelt es sich um eine Person, die Microsoft Teams in einer anderen Organisation verwendet und zur Teilnahme an einer Besprechung eingeladen wurde, jedoch keinen Zugriff auf andere freigegebene Ressourcen Ihrer Organisation hat. Externe Teilnehmer werden in der Besprechungsliste mit dem gleichen Identitätsnamen wie in ihrer eigenen Organisation angezeigt. Weitere Informationen zu externen Teilnehmern erhalten Sie unter [Kommunikation mit Benutzern aus anderen Organisationen](communicate-with-users-from-other-organizations.md#external-access).

| Live-Ereignis |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
|  **Feature**         | Vor der Besprechung | Während der Besprechung | Nach der Besprechung |
| Chat | Nicht zutreffend| Nicht zutreffend | Nicht zutreffend |
| Besprechungsnotizen | Nein | Nein | Nein |
| Whiteboard | Nein| Nein | Nein |
| Aufzeichnung läuft | Nicht zutreffend | Nein | Nein |
| Dateien | Ja | Ja | Ja |
|||||||

### <a name="anonymous-participant"></a>Anonyme Teilnehmer

Ein anonymer Teilnehmer ist wie ein externer Benutzer, seine Identität wird jedoch nicht in der Besprechung angezeigt. Zum Zeitpunkt des Beitritts gibt er manuell einen Nickname ein. Mehr über anonyme Teilnehmer erfahren Sie unter [Sicherheit und Microsoft Teams](teams-security-guide.md#participant-types).

| Live-Ereignis|  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **Feature**        | Vor der Besprechung | Während der Besprechung | Nach der Besprechung |
| Chat | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend |
| Besprechungsnotizen | Nicht zutreffend | Nein | Nicht zutreffend |
| Whiteboard | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend |
| Aufzeichnung läuft | Nicht zutreffend | Nein | Nicht zutreffend |
| Dateien | Nicht zutreffend | Nein | Nicht zutreffend |
|||||||


## <a name="related-topics"></a>Verwandte Themen

[Sicherheit und Microsoft Teams](teams-security-guide.md)

[Gastzugriff in Teams](guest-access.md)

[Planen von Liveereignissen in Teams](teams-live-events/plan-for-teams-live-events.md)
