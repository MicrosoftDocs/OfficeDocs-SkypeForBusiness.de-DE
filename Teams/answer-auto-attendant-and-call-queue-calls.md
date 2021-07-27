---
title: Beantworten von automatischen Telefonkonferenzen und Anrufen in der Anrufwarteschleife
ms.reviewer: colongma
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: Beschreibt automatische Telefonkonferenzen in der Cloud und Anrufwarteschleifen und erläutert, wie Sie diese Anrufe in einem Teams.
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
ms.openlocfilehash: 6e7f20bc34b22449a115b0742a7cfdac88792f4c
ms.sourcegitcommit: d34dbdc2f71f3d024cb7f1856fc0f8bbc701f66d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2021
ms.locfileid: "53506394"
---
# <a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a>Direktes Beantworten von Anrufen aus der automatischen Telefonzentrale und der Anrufwarteschleife aus Teams

Teams Benutzer können Anrufe von automatischen Cloud-Telefonkonferenzen und Anrufwarteschleifen direkt über ihren eigenen Teams beantworten.

## <a name="what-are-auto-attendants-and-call-queues"></a>Was sind automatische Telefonkonferenzen und Anrufwarteschleifen?

Automatische Cloud-Telefonkonferenzen bieten eine Reihe von Sprachanrufen oder eine Audiodatei, die Anrufer hören, statt einer menschlichen Telefongesellschaft, wenn sie sich in eine Organisation einmingen. Bei einer automatischen Telefonzentrale können die Anrufer durch das Menüsystem navigieren, Anrufe einleiten oder Benutzer suchen, indem sie eine Wähltastatur eines Telefons (MFV) oder Spracheingaben mit Spracherkennung verwenden.

Cloudanrufwarteschleifen beinhalten die beim Wählen einer Telefonnummer Ihrer Organisation verwendeten Begrüßungen, die Möglichkeit, den Anruf automatisch zu halten und nach dem nächsten verfügbaren Telefonisten zu suchen, um den Anruf zu entgegenzunehmen, während die Anrufe gehalten werden und die Anrufer dabei Musik hören. Sie können einzelne oder mehrere Anrufwarteschleifen für Ihre Organisation erstellen.

## <a name="handling-an-auto-attendant-or-call-queue-call"></a>Behandeln einer automatischen Telefonkonferenz oder eines Anrufwarteschleifenanrufs

Benutzer können eingehende Anrufe von einer automatischen Telefonant oder Anrufwarteschleife unterscheiden, bevor sie den Anruf entgegen nehmen. Zusammen mit dem Namen und/oder der Nummer des Anrufers enthält jeder Anruf Informationen darüber, wen der Anrufer zu erreichen versucht hat. So erhalten die Benutzer einen besseren Kontext für die Adressierung des Anrufers.

Die folgende Abbildung zeigt, wie ein eingehender Anruf von einer automatischen Telefonant oder Anrufwarteschleife für einen Benutzer angezeigt wird.

![Screenshot einer Benachrichtigung über einen eingehenden Anruf](media/answer-auto-attendant-and-call-queue-calls-image1.png)

Sobald eine automatische Telefonkonferenz oder ein Anrufwarteanruf beantwortet wurde, kann der Benutzer den Anruf wie jeden anderen Anruf &#x2014; er kann einen anderen Benutzer hinzufügen oder eine Telefonkonferenz einberaumen oder den Anruf an eine andere Partei durch stellen. Außerdem werden Anrufe der automatischen Telefon attendant basierend auf der Konfiguration des Benutzers weitergeleitet.

> [!NOTE] 
> Anrufe in die Anrufwarteschleife werden nicht basierend auf der Konfiguration des Benutzers weitergeleitet. Dadurch soll sichergestellt werden, dass Anrufer so lange in der Warteschleife verbleiben, bis ein Agent den Anruf beantworten kann und der Anrufer nicht unerwartet weitergeleitet wird.

> Die Agents werden bei verpassten Anrufen oder Voicemails für Anrufwarteschleifenanrufe nicht benachrichtigt.

## <a name="supported-clients"></a>Unterstützte Clients

Die folgenden Clients unterstützen automatische Telefonant- und Anrufwarteschleifenanrufe:

-    Microsoft Teams Windows-Client (32- und 64-Bit-Versionen)
-    Microsoft Teams Mac-Client
-    Microsoft Teams iPhone-App
-    Microsoft Teams Android-App

Der Teams-Client wird nur mit dem [Koexistenzmodus Teams unterstützt.](/microsoftteams/setting-your-coexistence-and-upgrade-settings)

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a>Konfigurieren der automatischen Telefon attendant- und Anrufwarteschleifenunterstützung für Microsoft Teams

Um Anrufe in der automatischen Telefonwarteschleife Microsoft Teams Anrufwarteschleifenanrufe zu empfangen, müssen Sie Ihre Interoperabilitätsrichtlinie und die Upgraderichtlinie konfigurieren. Lesen Sie [bitte Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business.](migration-interop-guidance-for-teams-with-skype.md) Wenn Sie keine automatische Telefonhalterung und/oder Anrufwarteschleife konfiguriert [](create-a-phone-system-auto-attendant.md) haben und dies tun möchten, lesen Sie Einrichten einer automatischen Cloud-Telefonkonferenz und Erstellen einer [Cloudanrufwarteschleife.](create-a-phone-system-call-queue.md)

## <a name="known-issues"></a>Bekannte Probleme

Wenn ein Telefonwarteschlangen-Agents einen Anruf auf dem mobilen Gerät erhält, werden die Anrufe möglicherweise in den Halteschleifen bleiben, wenn das Gerät gesperrt ist. Der Benutzer muss zuerst das Gerät entsperren und den Anruf dann beantworten.


## <a name="related-topics"></a>Verwandte Themen

-    [Was ist Telefonsystem in Microsoft 365 oder Office 365](what-is-phone-system-in-office-365.md)
-    [Erstellen einer Cloudanrufwarteschleife](create-a-phone-system-call-queue.md)
-    [Was sind automatische Cloudtelefonzentralen?](what-are-phone-system-auto-attendants.md)
-    [Einrichten einer automatischen Cloudtelefonzentrale](create-a-phone-system-auto-attendant.md)

