---
title: Beantworten von automatischen Telefonkonferenz- und Anrufwarteschlangeanrufen
ms.reviewer: colongma
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: Beschreibt automatische Cloud-Telefonkonferenzen und Anrufwarteschlangen und erläutert, wie Sie diese Anrufe in Teams beantworten können.
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
ms.openlocfilehash: cca068ab1194a48eb775550e4bf3f99826d82d2a
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2021
ms.locfileid: "50874665"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a>Direktes Beantworten von Anrufen aus der automatischen Telefonzentrale und der Anrufwarteschleife aus Teams
===========================================================

Teams-Benutzer können Anrufe von automatischen Cloud-Telefonkonferenzen und Anrufwarteschlangen direkt über ihren Teams-Client empfangen und beantworten.

## <a name="what-are-auto-attendants-and-call-queues"></a>Was sind automatische Telefonkonferenzen und Anrufwarteschlangen?

Automatische Cloud attendants provide a series of voice prompts or a audio file that callers hear instead of a human operator when they call in to an organization. Bei einer automatischen Telefonzentrale können die Anrufer durch das Menüsystem navigieren, Anrufe einleiten oder Benutzer suchen, indem sie eine Wähltastatur eines Telefons (MFV) oder Spracheingaben mit Spracherkennung verwenden.

Cloudanrufwarteschleifen beinhalten die beim Wählen einer Telefonnummer Ihrer Organisation verwendeten Begrüßungen, die Möglichkeit, den Anruf automatisch zu halten und nach dem nächsten verfügbaren Telefonisten zu suchen, um den Anruf zu entgegenzunehmen, während die Anrufe gehalten werden und die Anrufer dabei Musik hören. Sie können einzelne oder mehrere Anrufwarteschleifen für Ihre Organisation erstellen.

## <a name="handling-an-auto-attendant-or-call-queue-call"></a>Behandeln einer automatischen Telefonkonferenz oder eines Anrufwarteschlangenanrufs

Benutzer können eingehende Anrufe von einer automatischen Telefonkonferenz oder Anrufwarteschlange unterscheiden, bevor sie den Anruf entgegen nehmen. Zusammen mit dem Namen und/oder der Nummer des Anrufers enthält jeder Anruf Informationen darüber, wen der Anrufer erreichen wollte, um den Benutzern einen besseren Kontext für die Adressierung des Anrufers zu bieten.

Die folgende Abbildung zeigt, wie ein eingehender Anruf von einer automatischen Telefonwarteschlange oder Anrufwarteschlange für einen Benutzer angezeigt wird.

![Screenshot einer Benachrichtigung über eingehenden Anruf](media/answer-auto-attendant-and-call-queue-calls-image1.png)

Sobald eine automatische Telefonkonferenz oder ein Anrufwarteschlangeanruf beantwortet wurde, kann der Benutzer den Anruf wie jeden anderen Anruf verarbeiten &#x2014; er kann einen anderen Benutzer hinzufügen oder eine Konferenz starten oder den Anruf an eine andere Partei übertragen. Außerdem werden automatische Telefonanrufe basierend auf der Konfiguration des Benutzers weitergeleitet.

> [!NOTE] 
> Anrufwarteschlangenanrufe werden nicht basierend auf der Konfiguration des Benutzers weitergeleitet. Dadurch wird sichergestellt, dass Anrufer in der Warteschlange verbleiben, bis ein Agent den Anruf beantworten kann und der Anrufer nicht unerwartet weitergeleitet wird.

> Agents werden nicht über verpasste Anrufe oder Voicemails für Anrufwarteschlangenanrufe benachrichtigt.

## <a name="supported-clients"></a>Unterstützte Clients

Unterstützung für automatische Telefonkonferenzen und Anrufwarteschlangenanrufe ist in den folgenden Clients verfügbar:

-    Microsoft Teams Windows-Client (32- und 64-Bit-Versionen)
-    Microsoft Teams Mac-Client
-    Microsoft Teams iPhone-App
-    Microsoft Teams Android-App

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a>Konfigurieren der automatischen Telefonkonferenz und Anrufwarteschlange für Microsoft Teams

Zum Empfangen von automatischen Telefonanrufen und Anrufwarteschlangenanrufen in Microsoft Teams müssen Sie Ihre Interoperabilitätsrichtlinie und Upgraderichtlinie konfigurieren. Lesen Sie [Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden.](migration-interop-guidance-for-teams-with-skype.md) Wenn Sie keine automatische Telefonkonferenz und/oder Anrufwarteschlange konfiguriert [](create-a-phone-system-auto-attendant.md) haben und dies tun möchten, lesen Sie Einrichten einer automatischen Cloud-Telefonkonferenz und Erstellen einer Cloudanrufwarteschlange. [](create-a-phone-system-call-queue.md)

## <a name="known-issues"></a>Bekannte Probleme

Wenn ein Anrufwarteschlange-Agent einen Anruf auf dem mobilen Gerät empfängt, werden Anrufe möglicherweise in den Halteraum gestellt, wenn das Gerät gesperrt ist. Der Benutzer muss zuerst das Gerät entsperren und dann den Anruf beantworten.


## <a name="related-topics"></a>Verwandte Themen

-    [Was ist Telefonsystem in Microsoft 365 oder Office 365?](what-is-phone-system-in-office-365.md)
-    [Erstellen einer Cloudanrufwarteschleife](create-a-phone-system-call-queue.md)
-    [Was sind automatische Cloudtelefonzentralen?](what-are-phone-system-auto-attendants.md)
-    [Einrichten einer automatischen Cloudtelefonzentrale](create-a-phone-system-auto-attendant.md)

