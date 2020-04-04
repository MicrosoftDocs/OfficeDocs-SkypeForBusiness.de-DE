---
title: Annehmen einer automatischen Telefonzentrale und Anruf Warteschlangen Anrufe
ms.reviewer: waseemh
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: ITPro
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: Beschreibt automatische Cloud-Telefonzentralen und Anrufwarteschlangen und erläutert, wie Sie diese Anrufe in Teams annehmen können.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d630ea41915cb89013e407a6fa0b1cc21cb21abf
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137435"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a>Direktes Beantworten von Anrufen aus der automatischen Telefonzentrale und der Anrufwarteschleife aus Teams
===========================================================

Benutzer von Teams können Anrufe von automatischen Cloud-Telefonzentralen empfangen und annehmen sowie Warteschlangen direkt von Ihrem Team-Client aus anrufen. Für Benutzer von Teams ist das Feature für die automatische Telefonzentrale jetzt in der Regel verfügbar, und die Anruf Warteschlangenfunktion befindet sich in der Vorschau. 

## <a name="what-are-auto-attendants-and-call-queues"></a>Was sind automatische Telefonzentralen und Anrufwarteschlangen?

Automatische Cloud-Telefonzentralen bieten eine Reihe von Sprachansagen oder eine Audiodatei, die Anrufer hören, anstatt einen menschlichen Operator zu hören, wenn Sie sich in eine Organisation einwählen. Bei einer automatischen Telefonzentrale können die Anrufer durch das Menüsystem navigieren, Anrufe einleiten oder Benutzer suchen, indem sie eine Wähltastatur eines Telefons (MFV) oder Spracheingaben mit Spracherkennung verwenden.

Cloudanrufwarteschleifen beinhalten die beim Wählen einer Telefonnummer Ihrer Organisation verwendeten Begrüßungen, die Möglichkeit, den Anruf automatisch zu halten und nach dem nächsten verfügbaren Telefonisten zu suchen, um den Anruf zu entgegenzunehmen, während die Anrufe gehalten werden und die Anrufer dabei Musik hören. Sie können einzelne oder mehrere Anrufwarteschleifen für Ihre Organisation erstellen.

## <a name="handling-an-auto-attendant-or-call-queue-call"></a>Behandeln einer automatischen Telefonzentrale oder eines Anruf Warteschlangen Anrufs

Benutzer können eingehende Anrufe von einer automatischen Telefonzentrale oder Anrufwarteschlange unterscheiden, bevor Sie den Anruf annehmen. Zusammen mit dem Namen und/oder der Nummer des Anrufers enthält jeder Anrufinformationen darüber, wer der Anrufer zu erreichen versucht hat, sodass die Benutzer einen besseren Kontext für die Adressierung des Anrufers erhalten.

Die folgende Abbildung zeigt, wie ein eingehender Anruf von einer automatischen Telefonzentrale oder einer Anrufwarteschlange für einen Benutzer angezeigt wird.

![Screenshot einer Benachrichtigung über eingehende Anrufe](media/answer-auto-attendant-and-call-queue-calls-image1.png)

Sobald eine automatische Telefonzentrale oder ein Anruf Warteschlangen Anruf beantwortet wurde, kann der Benutzer den Anruf wie jeden anderen Anruf verarbeiten, &#x2014; er einem anderen Benutzer hinzufügen oder eine Konferenz durchführen oder den Anruf an eine andere Person übertragen kann. Darüber hinaus werden Anrufe an die automatische Telefonzentrale basierend auf der Konfiguration des Benutzers weitergeleitet.

> [!NOTE] 
> Anruf Warteschlangen Anrufe werden nicht basierend auf der Konfiguration des Benutzers weitergeleitet. Dadurch wird sichergestellt, dass Anrufer in der Warteschlange verbleiben, bis ein Agent den Anruf annehmen kann und der Anrufer nicht unerwartet weitergeleitet wird.

## <a name="supported-clients"></a>Unterstützte Clients

Unterstützung für automatische Telefonzentrale und Anruf Warteschlangen Anrufe steht in den folgenden Clients zur Verfügung:

-    Microsoft Teams Windows-Client (32- und 64-Bit-Versionen)
-    Microsoft Teams Mac-Client
-    Microsoft Teams-iPhone-App
-    Microsoft Teams Android-App

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a>Konfigurieren der automatischen Telefonzentrale und der Unterstützung der Anrufwarteschlange für Microsoft Teams

Wenn Sie die automatische Telefonzentrale und die Anruf Warteschlangen Anrufe in Microsoft Teams empfangen möchten, müssen Sie Ihre Interoperabilitätsrichtlinie und die Upgrade-Richtlinie konfigurieren. Bitte überprüfen Sie [Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](migration-interop-guidance-for-teams-with-skype.md). Wenn Sie keine automatische Telefonzentrale und/oder keine Anrufwarteschlange konfiguriert haben und dies tun möchten, lesen Sie [Einrichten einer automatischen Cloud-Telefonzentrale](create-a-phone-system-auto-attendant.md) und [Erstellen einer Cloud-Anrufwarteschlange](create-a-phone-system-call-queue.md).

## <a name="related-topics"></a>Verwandte Themen

-    [Was ist das Telefon System in Office 365?](what-is-phone-system-in-office-365.md)
-    [Erstellen einer Cloudanrufwarteschleife](create-a-phone-system-call-queue.md)
-    [Was sind automatische Cloudtelefonzentralen?](what-are-phone-system-auto-attendants.md)
-    [Einrichten einer automatischen Cloudtelefonzentrale](create-a-phone-system-auto-attendant.md)

