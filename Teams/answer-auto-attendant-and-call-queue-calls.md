---
title: Annehmen automatischer Telefonzentralen- und Anrufwarteschleifenanrufe
ms.reviewer: colongma
author: CarolynRowe
ms.author: crowe
manager: serdars
audience: ITPro
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: Beschreibt automatische Cloudtelefonzentralen und Anrufwarteschleifen und erläutert, wie Sie diese Anrufe in Teams annehmen können.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1a9058dbd583c9d795d04f27b43995c75095e80d
ms.sourcegitcommit: 90f03a841f8ca33092dce65c543357c7c2f7b82a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2022
ms.locfileid: "66647667"
---
# <a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a>Direktes Beantworten von Anrufen aus der automatischen Telefonzentrale und der Anrufwarteschleife aus Teams

Teams-Benutzer können Anrufe von automatischen Cloud-Telefonzentralen und Anrufwarteschleifen direkt von ihrem Teams-Client empfangen und beantworten.

## <a name="what-are-auto-attendants-and-call-queues"></a>Was sind automatische Telefonzentralen und Anrufwarteschleifen?

Automatische Cloudtelefonzentralen stellen eine Reihe von Sprachansagen oder eine Audiodatei bereit, die Anrufer hören, anstatt einen menschlichen Operator, wenn sie sich in eine Organisation einwägen. Bei einer automatischen Telefonzentrale können die Anrufer durch das Menüsystem navigieren, Anrufe einleiten oder Benutzer suchen, indem sie eine Wähltastatur eines Telefons (MFV) oder Spracheingaben mit Spracherkennung verwenden.

Cloudanrufwarteschleifen beinhalten die beim Wählen einer Telefonnummer Ihrer Organisation verwendeten Begrüßungen, die Möglichkeit, den Anruf automatisch zu halten und nach dem nächsten verfügbaren Telefonisten zu suchen, um den Anruf zu entgegenzunehmen, während die Anrufe gehalten werden und die Anrufer dabei Musik hören. Sie können einzelne oder mehrere Anrufwarteschleifen für Ihre Organisation erstellen.

## <a name="handling-an-auto-attendant-or-call-queue-call"></a>Behandeln eines automatischen Telefonzentralen- oder Anrufwarteschleifenanrufs

Benutzer können eingehende Anrufe von einer automatischen Telefonzentrale oder Anrufwarteschleife unterscheiden, bevor sie den Anruf annehmen. Zusammen mit dem Namen und/oder der Nummer des Anrufers enthält jeder Anruf Informationen darüber, wen der Anrufer erreichen wollte, wodurch benutzer einen besseren Kontext für die Ansprache des Anrufers erhalten.

Die folgende Abbildung zeigt, wie ein eingehender Anruf von einer automatischen Telefonzentrale oder Anrufwarteschleife einem Benutzer angezeigt wird.

![Screenshot einer Benachrichtigung über einen eingehenden Anruf.](media/answer-auto-attendant-and-call-queue-calls-image1.png)

Sobald eine automatische Telefonzentrale oder ein Anruf in der Anrufwarteschleife angenommen wurde, kann der Benutzer den Anruf wie jeder andere Anruf verarbeiten, &#x2014; er einen anderen Benutzer hinzufügen oder eine Konferenz durchführen oder den Anruf an eine andere Partei weiterleiten kann. Außerdem werden automatische Telefonzentralenanrufe basierend auf der Konfiguration des Benutzers weitergeleitet.

> [!NOTE] 
> Anrufwarteschleifenanrufe werden nicht basierend auf der Konfiguration der Anrufbeantwortungsregeln des Benutzers weitergeleitet. Dadurch wird sichergestellt, dass Anrufer in der Warteschleife bleiben, bis ein Agent den Anruf annehmen kann und der Anrufer nicht unerwartet weitergeleitet wird.
>
> Benutzer, die Anrufe von automatischen Telefonzentralen und Anrufwarteschleifen erhalten, erhalten nur dann den Namen des Anrufers, wenn er aus dem PSTN bereitgestellt wird oder wenn die Nummer des Anrufers mit den Clientkontakten des lokalen Teams des Zielbenutzers übereinstimmt.
>
> Agents werden nicht über verpasste Anrufe oder Voicemails für Anrufwarteschleifenanrufe benachrichtigt.

## <a name="supported-clients"></a>Unterstützte Clients

Unterstützung für automatische Telefonzentralen- und Anrufwarteschleifenanrufe ist in den folgenden Clients verfügbar:

-    Microsoft Teams Windows-Client (32- und 64-Bit-Versionen)
-    Microsoft Teams Mac-Client
-    Microsoft Teams iPhone-App
-    Microsoft Teams Android-App

Der Teams-Client wird nur mit einem [Koexistenzmodus von "Nur Teams](/microsoftteams/setting-your-coexistence-and-upgrade-settings)" unterstützt.

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a>Konfigurieren der Unterstützung für automatische Telefonzentrale und Anrufwarteschleife für Microsoft Teams

Um Anrufe von automatischen Telefonzentralen und Anrufwarteschleifen in Microsoft Teams zu erhalten, müssen Sie Ihre Interoperabilitätsrichtlinie und Upgraderichtlinie konfigurieren. Überprüfen Sie [die Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](migration-interop-guidance-for-teams-with-skype.md). Wenn Sie keine automatische Telefonzentrale und/oder Anrufwarteschleife konfiguriert haben und dies tun möchten, lesen Sie " [Einrichten einer automatischen Cloudtelefonzentrale](create-a-phone-system-auto-attendant.md) " und ["Erstellen einer Cloudanrufwarteschleife](create-a-phone-system-call-queue.md)".

## <a name="known-issues"></a>Bekannte Probleme

Wenn ein Anrufwarteschleifen-Agent einen Anruf auf dem mobilen Gerät empfängt, wird der Anruf möglicherweise gehalten, wenn das Gerät gesperrt ist. Benutzer müssen das Gerät zuerst entsperren und dann den Anruf annehmen.


## <a name="related-topics"></a>Verwandte Themen

[Erstellen einer Cloudanrufwarteschleife](create-a-phone-system-call-queue.md)

[Was sind automatische Cloudtelefonzentralen?](what-are-phone-system-auto-attendants.md)

[Einrichten einer automatischen Cloudtelefonzentrale](create-a-phone-system-auto-attendant.md)

