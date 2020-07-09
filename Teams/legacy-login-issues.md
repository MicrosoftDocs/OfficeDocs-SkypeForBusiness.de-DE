---
title: Probleme beim Empfangen von Nachrichten und Anrufen auf Legacysystemen in Teams
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 05/29/2020
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: Behandeln von Problemen im Zusammenhang mit dem empfangen von Nachrichten und Anrufen auf Legacysystemen
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: af7845b5fd6d50d63be6cd21749cbfedc7669fcf
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085151"
---
<a name="issues-receiving-messages-and-calls-on-legacy-systems"></a><span data-ttu-id="33ef2-103">Probleme beim Empfangen von Nachrichten und Anrufen auf Legacysystemen</span><span class="sxs-lookup"><span data-stu-id="33ef2-103">Issues receiving messages and calls on legacy systems</span></span>
==============================================================

<span data-ttu-id="33ef2-104">Möglicherweise haben die Benutzer Probleme beim Empfangen von Nachrichten oder anrufen, wenn Sie ältere Versionen von Teams verwenden oder sich mit anderen Anwendungen angemeldet haben.</span><span class="sxs-lookup"><span data-stu-id="33ef2-104">Users might have issues receiving messages or calls if they are using older versions of Teams or have logged in with other applications.</span></span>

## <a name="legacy-adu-setups"></a><span data-ttu-id="33ef2-105">Legacy-Adu-Setups</span><span class="sxs-lookup"><span data-stu-id="33ef2-105">Legacy ADU setups</span></span>

 <span data-ttu-id="33ef2-106">Wenn Benutzer bei einem in eine Domäne eingebundenen Computer angemeldet sind und **Sie nicht möchten, dass ihre Benutzernamen im Anmeldebildschirm von Microsoft Teams vorab ausgefüllt werden**, können Administratoren die folgende Windows-Registrierung so einrichten, dass das Vorab-Ausfüllen des Benutzernamens (UPN) deaktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="33ef2-106">If users are signed in to a domain-joined computer and you **don't want their user name pre-populated on the Teams sign-in screen**, admins can set the following Windows registry to turn off pre-population of the user name (UPN):</span></span>

  <span data-ttu-id="33ef2-107">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span><span class="sxs-lookup"><span data-stu-id="33ef2-107">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span></span><br/>
  <span data-ttu-id="33ef2-108">SkipUpnPrefill(REG_DWORD)</span><span class="sxs-lookup"><span data-stu-id="33ef2-108">SkipUpnPrefill(REG_DWORD)</span></span><br/>
  <span data-ttu-id="33ef2-109">0x00000001 (1)</span><span class="sxs-lookup"><span data-stu-id="33ef2-109">0x00000001 (1)</span></span>

> [!NOTE]
> <span data-ttu-id="33ef2-110">Das Überspringen oder Ignorieren des Vorab-Ausfüllens von Benutzernamen ist für Benutzernamen, die in „.local“ oder „.corp“ enden, standardmäßig aktiviert, daher müssen Sie keinen Registrierungsschlüssel festlegen, um diese zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="33ef2-110">Skipping or ignoring user name pre-fill for user names that end in ".local" or ".corp" is on by default, so you don't need to set a registry key to turn these off.</span></span>

<span data-ttu-id="33ef2-111">Weitere Informationen finden Sie unter [Anmelden bei Microsoft Teams mithilfe der modernen Authentifizierung](sign-in-teams.md) .</span><span class="sxs-lookup"><span data-stu-id="33ef2-111">See [Sign in to Microsoft Teams using modern authentication](sign-in-teams.md) for more information.</span></span>

## <a name="skype-token-revocation"></a><span data-ttu-id="33ef2-112">Skype-Token-Sperrung</span><span class="sxs-lookup"><span data-stu-id="33ef2-112">Skype token revocation</span></span>

<span data-ttu-id="33ef2-113">Wenn ein Kennwort geändert/zurückgesetzt wird, erhalten ältere Clients keine Nachrichten und Anrufe bis zu einer Stunde.</span><span class="sxs-lookup"><span data-stu-id="33ef2-113">When changing/resetting a password, older clients will not receive messages and calls for up to an hour.</span></span> <span data-ttu-id="33ef2-114">Um dieses Problem zu beheben, starten Sie die APP entweder neu, oder wechseln Sie zu neueren Clients.</span><span class="sxs-lookup"><span data-stu-id="33ef2-114">To resolve this issue, either restart the app or move to newer clients.</span></span>


## <a name="related-topics"></a><span data-ttu-id="33ef2-115">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="33ef2-115">Related topics</span></span>

[<span data-ttu-id="33ef2-116">Teams-Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="33ef2-116">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)