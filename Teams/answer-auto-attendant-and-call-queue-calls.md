---
title: Beantworten Sie die automatische Telefonzentrale, und rufen Sie die Warteschlange Anrufe direkt von Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/20/2018
ms.topic: article
ms.service: msteams
description: Beschreibt Telefonsystem automatischen Telefonzentralen und Anruf Warteschlangen und erläutert, wie Sie diese Aufrufe in Teams beantworten können.
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7b0b533020def2e344991fa758304888c8166436
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2018
ms.locfileid: "25839205"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a>Beantworten Sie die automatische Telefonzentrale, und rufen Sie die Warteschlange Anrufe direkt von Teams
===========================================================

Teams Benutzer können empfangen und Entgegennehmen von Anrufen von Skype für Business Online automatische Telefonzentrale und Warteschlangen direkt von ihrem Client Teams aufrufen. Für Benutzer von Teams die automatische Telefonzentrale-Funktion ist jetzt erhältlich, und die Anruf-Warteschlange-Funktion ist in der Vorschau. 

## <a name="what-are-auto-attendants-and-call-queues"></a>Was sind automatische um-Telefonzentralen und Warteschlangen aufrufen?

Telefon System automatischen Telefonzentralen bieten eine Reihe von Ansagen oder einer Audiodatei, die anstelle einer human Operator Anrufer hören, wenn sie zu einer Organisation anrufen. Bei einer automatischen Telefonzentrale können die Anrufer durch das Menüsystem navigieren, Anrufe einleiten oder Benutzer suchen, indem sie eine Wähltastatur eines Telefons (MFV) oder Spracheingaben mit Spracherkennung verwenden.

System-Telefonanruf Warteschlangen enthalten Ansage, die verwendet werden, wenn angerufen eine Rufnummer für Ihre Organisation die Möglichkeit, die Anrufe automatisch gehalten wird und für den nächsten verfügbaren Anruf-Agent zum Verarbeiten des Anrufs beim Personen die Möglichkeit zum Suchen, die Anruf Musik in der Warteschleife hören sind. Sie können einzelne oder mehrere Anruf Warteschlangen für Ihre Organisation erstellen.

## <a name="handling-an-auto-attendant-or-call-queue-call"></a>Behandeln von einem Anruf automatische Telefonzentrale oder ein Anruf Warteschlange

Benutzer können eingehende Anrufe von einer automatischen Telefonzentrale oder ein Anruf Warteschlange unterscheiden, bevor sie den Anruf annehmen. Jeden Anruf wird zusammen mit den Namen und/oder die Nummer des Anrufers Informationen, die der Anrufer versucht hat, zu erreichen, den Benutzern ermöglicht, eines besseren Kontexts zum Umgang mit des Anrufers enthalten.

Die folgende Abbildung zeigt, wie ein Anruf von eine automatische Telefonzentrale oder ein Anruf Warteschlange, die einem Benutzer angezeigt wird.

![Benachrichtigung über eingehende Anrufe](media/answer-auto-attendant-and-call-queue-calls-image1.png)

Nachdem ein automatische Telefonzentrale oder ein Anruf-Warteschlange Anruf entgegengenommen wurde, kann der Benutzer den Anruf wie alle anderen Anruf & #x 2014 verarbeiten; Sie können hinzufügen oder einer Konferenz in einem anderen Benutzer oder den Anruf an eine andere Person weiterleiten. Darüber hinaus werden basierend auf der Konfiguration des Benutzers Auto attendant Anrufe weitergeleitet werden.

> [!NOTE] 
> Anruf Warteschlange Anrufe werden nicht weitergeleitet, je nach Konfiguration des Benutzers. Dadurch wird sichergestellt, Anrufer verbleiben in der Warteschlange, bis ein Agent den Anruf entgegennehmen kann, und der Aufrufer ist nicht unerwartet weitergeleitet.

## <a name="supported-clients"></a>Unterstützte clients

Unterstützung für die automatische Telefonzentrale und Anruf Warteschlange Anrufe ist in die folgenden Clients verfügbar:

-   Microsoft Teams Windows-Client (32- und 64-Bit-Versionen)
-   Microsoft Teams Mac-Client
-   Microsoft-Teams, iPhone-app
-   Microsoft-Teams, Android-app

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a>Konfigurieren der Auto Attendant, und rufen Warteschlange-Unterstützung für Microsoft-Teams

Um-Telefonzentrale erhalten, und rufen Sie Warteschlange Anrufe für Microsoft-Teams, müssen Sie Ihre Interoperabilität Richtlinie konfigurieren und Aktualisieren der Richtlinie. Überprüfen Sie die [Migration und Interoperabilität für Organisationen mit Teams zusammen mit Skype für Unternehmen](migration-interop-guidance-for-teams-with-skype.md). Wenn Sie keinen automatischen Telefonzentrale und/oder Anruf Warteschlange konfiguriert und dazu möchten, finden Sie unter [Richten Sie eine automatische Telefonzentrale Telefonsystem](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant) und [eine Telefonsystem Anruf Warteschlange zu erstellen](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).

## <a name="related-topics"></a>Verwandte Themen

-   [Was ist Telefonsystem in Office 365](what-is-phone-system-in-office-365.md)
-   [Erstellen einer Telefonsystem-Anrufwarteschleife](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)
-   [Was sind automatische Telefonzentralen für das Telefonsystem?](what-are-phone-system-auto-attendants.md)
-   [Einrichten einer automatischen Telefonzentrale für das Telefonsystem](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

