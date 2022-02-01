---
title: Verwenden Sie den Gastzugriff und den externen Zugriff, um mit Personen außerhalb Ihres Unternehmens zusammenzuarbeiten
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: vinbel, luises
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: high
description: Erfahren Sie, wie Sie Benutzer aus anderen Organisationen in Microsoft Teams mithilfe des externen (Partnerverbund) und des Gastzugriffs anrufen, mit ihnen chatten, sie finden und hinzufügen können.
ms.openlocfilehash: ab6a15edc1aa8d0de6f77b96ed176171ff5d65ae
ms.sourcegitcommit: 159399f2325af644c20551925c1fa34bf76aad43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2022
ms.locfileid: "62288433"
---
# <a name="use-guest-access-and-external-access-to-collaborate-with-people-outside-your-organization"></a>Verwenden Sie den Gastzugriff und den externen Zugriff, um mit Personen außerhalb Ihres Unternehmens zusammenzuarbeiten

Wenn Sie mit Personen außerhalb Ihrer Organisation kommunizieren und zusammenarbeiten müssen, bietet Ihnen Microsoft Teams dafür zwei Optionen:

- **Externer Zugriff** – Ein Typ des Partnerverbunds, der es Benutzern erlaubt, Personen in anderen Organisationen zu finden, sie anzurufen und mit ihnen zu chatten. Diese Personen können nicht zu Teams hinzugefügt werden, außer wenn sie als Gäste eingeladen werden.
- **Gastzugriff** – Mit dem Gastzugriff können Sie Personen von außerhalb Ihrer Organisation einladen, einem Team beizutreten. Eingeladene Personen erhalten ein Gastkonto im Azure Active Directory.

Beachten Sie, dass Teams Ihnen erlaubt, Personen von außerhalb Ihrer Organisation in Besprechungen einzuladen. Dafür muss kein externer oder Gastzugriff konfiguriert werden.

## <a name="external-access-federation"></a>Externer Zugriff (Partnerverbund)

Richten Sie externen Zugriff ein, wenn Sie Personen außerhalb Ihrer Organisation, die Teams, Skype for Business (online oder lokal) oder Skype verwenden, suchen, sie anrufen, mit ihnen chatten und Besprechungen mit ihnen einrichten müssen. 

Der externe Zugriff ist standardmäßig für alle Domänen aktiviert. Sie können den externen Zugriff einschränken, indem Sie bestimmte Domänen zulassen oder blockieren oder den Zugriff deaktivieren.

![Screenshot der Einstellungen für den externen Zugriff.](media/external-access-federation-settings.png)

Weitere Informationen zum Konfigurieren des externen Zugriffs finden Sie unter [Externen Zugriff verwalten](manage-external-access.md). 

>[!NOTE]
> Die Lizenzen von [Microsoft Teams kostenlos (klassisch)](https://support.microsoft.com/office/welcome-to-microsoft-teams-free-classic-6d79a648-6913-4696-9237-ed13de64ae3c) unterstützen keinen externen Zugriff.

## <a name="guest-access"></a>Gastzugriff

Verwenden Sie den Gastzugriff, um Personen von außerhalb Ihrer Organisation zu einem Team hinzuzufügen, in dem sie chatten, anrufen, treffen und an Dateien zusammenarbeiten können. Einem Gast können fast alle Funktionen des Teams gleich wie einem nativen Teammitglied zur Verfügung gestellt werden. Weitere Informationen finden Sie unter [Gasterfahrung in Teams](guest-experience.md).

Gäste werden dem Azure Active Directory Ihrer Organisation als B2B-Benutzer hinzugefügt und müssen sich mit ihrem Gastkonto in Teams anmelden. Dies bedeutet, dass sie sich möglicherweise in seiner eigenen Organisation abmelden müssen, um sich bei Ihrer Organisation anzumelden.

Informationen zum Konfigurieren des Gastzugriffs für Teams finden Sie unter [Zusammenarbeit mit Gästen in einem Team](/microsoft-365/solutions/collaborate-as-team).

## <a name="compare-external-and-guest-access"></a>Vergleich zwischen externem Zugriff und Gastzugriff

Die folgende Tabelle zeigt die Unterschiede zwischen dem externen Zugriff (Partnerverbund) und Gästen. In beiden Fällen werden Personen von außerhalb Ihrer Organisation gegenüber Ihren Benutzern als „extern“ bezeichnet.

### <a name="things-your-users-can-do"></a>Dinge, die Ihre Benutzer tun können

| Benutzer können | Benutzer mit externem Zugriff | Gäste |
|---------|-----------------------|--------------------|
| Mit jemandem in einer anderen Organisation chatten | Ja | Ja |
| Jemanden in einer anderen Organisation anrufen | Ja | Ja |
| Sehen, ob jemand aus einer anderen Organisation für Anrufe oder Chats verfügbar ist | Ja | Ja<sup>1</sup> |
| Nach Personen in anderen Organisationen suchen | Ja<sup>2</sup> | Nein |
| Freigeben von Dateien | Nein | Ja |
| Die Abwesenheitsnachricht eines Mitarbeiters einer anderen Organisation anzeigen | Nein | Ja |
| Jemanden in einer anderen Organisation sperren  | Nein | Ja |
| Verwenden von @Erwähnungen | Ja<sup>3</sup> | Ja |

### <a name="things-people-outside-your-organization-can-do"></a>Dinge, die Personen von außerhalb der Organisation tun können

| Personen von außerhalb Ihrer Organisation können | Benutzer mit externem Zugriff | Gäste |
|---------|-----------------------|--------------------|
| Auf Teams-Ressourcen zugreifen | Nein | Ja |
| Zu einem Gruppenchat hinzugefügt werden | Ja | Ja |
| Zu einer Besprechung eingeladen werden | Ja | Ja |
| Private Anrufe führen | Ja | Ja<sup>5</sup> |
| Telefonnummer für Teilnehmer von Einwahlbesprechungen anzeigen | Nein<sup>4</sup> | Ja |
| IP-Video verwenden | Ja | Ja<sup>5</sup> |
| Bildschirmfreigabe verwenden | Ja<sup>3</sup> | Ja<sup>5</sup> |
| „Jetzt besprechen“ verwenden | Nein | Ja<sup>5</sup> |
| Gesendete Nachrichten bearbeiten | Ja<sup>3</sup> | Ja<sup>5</sup> |
| Gesendete Nachrichten löschen | Ja<sup>3</sup> | Ja<sup>5</sup> |
| Giphy in einer Unterhaltung verwenden | Ja<sup>3</sup> | Ja<sup>5</sup> |
| Memes in einer Unterhaltung verwenden | Ja<sup>3</sup> | Ja<sup>5</sup> |
| Sticker in einer Unterhaltung verwenden | Ja<sup>3</sup> | Ja<sup>5</sup> |
| Anwesenheit wird angezeigt | Ja | Ja |
| Verwenden von @Erwähnungen | Ja<sup>3</sup> | Ja |

<br>

<sup>1</sup> Vorausgesetzt, der Benutzer wurde als Gast hinzugefügt und hat sich mit dem Gastkonto angemeldet.<br>
<sup>2</sup> Nur per E-Mail- oder SIP-Adresse (Session Initiation Protocol).<br>
<sup>3</sup> Unterstützt für 1:1-Chat nur für Teams zu Teams-Benutzer aus zwei verschiedenen Organisation. <br>
<sup>4</sup> Standardmäßig können externe Teilnehmer die Telefonnummern der eingewählten Teilnehmer nicht sehen. Wenn Sie die Vertraulichkeit dieser Telefonnummern wahren wollen, wählen Sie **Töne** für **Typ der Ankündigungen von Ein-/Ausgängen** aus (dies verhindert, dass die Nummern von Teams ausgelesen werden). Weitere Informationen finden Sie unter [Aktivieren oder Deaktivieren von Ankündigungen bei Zu- oder Abgang für Besprechungen in Microsoft Teams](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md). <br>
<sup>5</sup> Standardmäßig zugelassen, kann aber vom Teams-Administrator deaktiviert werden

## <a name="related-topics"></a>Verwandte Themen

[Externer Zugriff in Teams](manage-external-access.md)

[Gastzugriff in Teams](guest-access.md)
