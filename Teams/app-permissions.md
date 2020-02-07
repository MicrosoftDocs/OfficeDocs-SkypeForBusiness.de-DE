---
title: Berechtigungen für Microsoft Teams-Apps und Überlegungen dazu
author: rmw2890
ms.author: rowille
manager: serdars
ms.date: 06/27/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
ms.reviewer: rowille
description: Hier erfahren Sie, welche Daten und Berechtigungen Apps von Ihrer Organisation anfordern.
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5d7548d4d162310bc239c752e2bce38e725008f9
ms.sourcegitcommit: 8e2fa7b744d0a174b699ae7298d4688b971eeff3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/07/2020
ms.locfileid: "41845226"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a><span data-ttu-id="b7a94-103">Berechtigungen für Microsoft Teams-Apps und Überlegungen dazu</span><span class="sxs-lookup"><span data-stu-id="b7a94-103">Microsoft Teams apps permissions and considerations</span></span>

<span data-ttu-id="b7a94-104">Microsoft Teams-Apps stellen eine Möglichkeit dar, eine oder mehrere Funktionen in einem _App-Paket_ zu aggregieren, das installiert, aktualisiert und deinstalliert werden kann.</span><span class="sxs-lookup"><span data-stu-id="b7a94-104">Microsoft Teams apps are a way to aggregate one or more capabilities into an _app package_ that can be installed, upgraded, and uninstalled.</span></span> <span data-ttu-id="b7a94-105">Zu diesen Funktionen gehören folgende:</span><span class="sxs-lookup"><span data-stu-id="b7a94-105">The capabilities include:</span></span>

- <span data-ttu-id="b7a94-106">Bots</span><span class="sxs-lookup"><span data-stu-id="b7a94-106">Bots</span></span>
- <span data-ttu-id="b7a94-107">Messagingerweiterungen</span><span class="sxs-lookup"><span data-stu-id="b7a94-107">Messaging extensions</span></span>
- <span data-ttu-id="b7a94-108">Registerkarten</span><span class="sxs-lookup"><span data-stu-id="b7a94-108">Tabs</span></span>
- <span data-ttu-id="b7a94-109">Connectors</span><span class="sxs-lookup"><span data-stu-id="b7a94-109">Connectors</span></span>

<span data-ttu-id="b7a94-110">Apps benötigen Einwilligungen der Benutzer und werden im Hinblick auf Richtlinien von der IT verwaltet.</span><span class="sxs-lookup"><span data-stu-id="b7a94-110">Apps are consented to by users and managed by IT from a policy perspective.</span></span> <span data-ttu-id="b7a94-111">Die Berechtigungen und das Risikoprofil einer App werden jedoch größtenteils durch die Berechtigungen und Risikoprofile der Funktionen definiert, die in der App enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="b7a94-111">However, for the most part, an app's permissions and risk profile are defined by the permissions and risk profiles of the capabilities that the app contains.</span></span> <span data-ttu-id="b7a94-112">Daher konzentriert sich dieser Artikel auf Berechtigungen und Überlegungen auf Funktionsebene.</span><span class="sxs-lookup"><span data-stu-id="b7a94-112">Therefore, this article focuses on permissions and considerations at the capability level.</span></span>

<span data-ttu-id="b7a94-113">Die unten in Großbuchstaben aufgeführten Berechtigungen, zum Beispiel RECEIVE_MESSAGE und REPLYTO_MESSAGE, werden in der [Entwicklerdokumentation für Microsoft Teams](https://aka.ms/teamsdevdocs) oder den [Berechtigungen für Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference) nicht erwähnt.</span><span class="sxs-lookup"><span data-stu-id="b7a94-113">The permissions listed below in capital letters, for example RECEIVE_MESSAGE and REPLYTO_MESSAGE, don't appear anywhere in the [Microsoft Teams developer documentation](https://aka.ms/teamsdevdocs) or the [permissions for Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).</span></span> <span data-ttu-id="b7a94-114">Es handelt sich einfach um eine nur in diesem Artikel verwendete beschreibende Kurzschreibweise.</span><span class="sxs-lookup"><span data-stu-id="b7a94-114">They're simply a descriptive shorthand for the purpose of this article.</span></span>


|    |     |
|-----------|------------|
| ![Ein Symbol, das einen Entscheidungspunkt darstellt](media/audio_conferencing_image7.png) <br/><span data-ttu-id="b7a94-116">Entscheidungspunkt</span><span class="sxs-lookup"><span data-stu-id="b7a94-116">Decision point</span></span>|<ul><li><span data-ttu-id="b7a94-117">Verwenden Sie die folgenden Tabellen als Leitfaden, um zu verstehen, welche Berechtigungen die apps, die Sie untersuchen, anfordern.</span><span class="sxs-lookup"><span data-stu-id="b7a94-117">Use the tables below as a guide to understand which permissions the apps you're investigating are requesting.</span></span></li></ul> |
| ![Ein Symbol, das den nächsten Schritt darstellt](media/audio_conferencing_image9.png)<br/><span data-ttu-id="b7a94-119">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="b7a94-119">Next step</span></span>|<ul><li><span data-ttu-id="b7a94-120">Untersuchen Sie die APP oder den Dienst selbst, um zu entscheiden, ob Sie in Ihrer Organisation Zugriff darauf gewähren möchten.</span><span class="sxs-lookup"><span data-stu-id="b7a94-120">Research the app or service itself to decide whether you want to allow access to it within your organization.</span></span> <span data-ttu-id="b7a94-121">So können Bots beispielsweise Nachrichten von Benutzern senden und empfangen und – mit Ausnahme der Enterprise-Unternehmens-Bots – außerhalb der Compliance-Grenze liegen.</span><span class="sxs-lookup"><span data-stu-id="b7a94-121">For example, bots send and receive messages from users, and—except for enterprise line-of-business bots—they're located outside the compliance boundary.</span></span> <span data-ttu-id="b7a94-122">Daher erfordert jede APP, die einen bot enthält, diese Berechtigungen und weist das Risikoprofil mindestens auf.</span><span class="sxs-lookup"><span data-stu-id="b7a94-122">Therefore, any app that includes a bot requires those permissions and has that risk profile, at a minimum.</span></span> </li></ul>|

## <a name="global-app-permissions-and-considerations"></a><span data-ttu-id="b7a94-123">Globale App-Berechtigungen und-Überlegungen</span><span class="sxs-lookup"><span data-stu-id="b7a94-123">Global app permissions and considerations</span></span>

### <a name="required-permissions"></a><span data-ttu-id="b7a94-124">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="b7a94-124">Required permissions</span></span>

<span data-ttu-id="b7a94-125">Keine</span><span class="sxs-lookup"><span data-stu-id="b7a94-125">None</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="b7a94-126">Optionale Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="b7a94-126">Optional permissions</span></span>

<span data-ttu-id="b7a94-127">Keine</span><span class="sxs-lookup"><span data-stu-id="b7a94-127">None</span></span>

### <a name="considerations"></a><span data-ttu-id="b7a94-128">Überlegungen</span><span class="sxs-lookup"><span data-stu-id="b7a94-128">Considerations</span></span>

<span data-ttu-id="b7a94-129">Eine APP muss offen legen, welche Daten Sie verwendet und wofür die Daten in den Nutzungsbedingungen und den Datenschutzrichtlinien Links verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b7a94-129">An app must disclose what data it uses and what the data is used for in its terms of use and privacy policy links.</span></span></td>

## <a name="bots-and-messaging-extensions"></a><span data-ttu-id="b7a94-130">Bots und Messaging-Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="b7a94-130">Bots and messaging extensions</span></span>

### <a name="required-permissions"></a><span data-ttu-id="b7a94-131">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="b7a94-131">Required permissions</span></span>

- <span data-ttu-id="b7a94-132">RECEIVE_MESSAGE, REPLYTO_MESSAGE:</span><span class="sxs-lookup"><span data-stu-id="b7a94-132">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="b7a94-133">Der Bot kann Nachrichten von Benutzern empfangen und auf diese antworten.<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b7a94-133">The bot can receive messages from users and reply to them.<sup>1</sup></span></span>

- <span data-ttu-id="b7a94-134">POST_MESSAGE_USER:</span><span class="sxs-lookup"><span data-stu-id="b7a94-134">POST_MESSAGE_USER.</span></span> <span data-ttu-id="b7a94-135">Nachdem ein Nutzer eine Nachricht an einen bot gesendet hat, kann der bot dem Nutzer direkte Nachrichten (auch als *proaktive Nachrichten* bezeichnet) senden.</span><span class="sxs-lookup"><span data-stu-id="b7a94-135">After a user has sent a message to a bot, the bot can send the user direct messages (also called *proactive messages* at any time.</span></span>

- <span data-ttu-id="b7a94-136">GET_CHANNEL_LIST:</span><span class="sxs-lookup"><span data-stu-id="b7a94-136">GET_CHANNEL_LIST.</span></span> <span data-ttu-id="b7a94-137">Bots, die zu Teams hinzugefügt wurden, können eine Liste der Namen und IDs der Kanäle in einem Team abrufen.</span><span class="sxs-lookup"><span data-stu-id="b7a94-137">Bots added to teams can get a list of names and IDs of the channels in a team.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="b7a94-138">Optionale Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="b7a94-138">Optional permissions</span></span>

- <span data-ttu-id="b7a94-139">Identität.</span><span class="sxs-lookup"><span data-stu-id="b7a94-139">IDENTITY.</span></span> <span data-ttu-id="b7a94-140">Wenn Sie in einem Kanal verwendet wird, können die APP-Bots auf grundlegende Identitätsinformationen von Teammitgliedern (Vorname, Nachname, Benutzerprinzipalname [UPN], e-Mail-Adresse) zugreifen. Wenn Sie in einem persönlichen oder Gruppen-Chat verwendet wird, kann der bot für diese Benutzer auf dieselben Informationen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="b7a94-140">When it's used in a channel, the app's bots can access basic identity information of team members (first name, last name, user principal name [UPN], email address); when it's used in a personal or group chat, the bot can access the same information for those users.</span></span>

- <span data-ttu-id="b7a94-141">POST_MESSAGE_TEAM.</span><span class="sxs-lookup"><span data-stu-id="b7a94-141">POST_MESSAGE_TEAM.</span></span> <span data-ttu-id="b7a94-142">Ermöglicht es den Bots einer APP, jederzeit direkte (proaktive) Nachrichten an ein beliebiges Teammitglied zu senden, auch wenn der Benutzer noch nie zuvor mit dem bot gesprochen hat.</span><span class="sxs-lookup"><span data-stu-id="b7a94-142">Allows an app's bots to send direct (proactive) messages to any team member at any time, even if the user has never talked to the bot before.</span></span>

- <span data-ttu-id="b7a94-143">Die folgenden sind keine expliziten Berechtigungen, sondern werden von RECEIVE_MESSAGE und REPLYTO_MESSAGE und den Bereichen impliziert, in denen die Bots verwendet werden können, die im Manifest deklariert werden:</span><span class="sxs-lookup"><span data-stu-id="b7a94-143">The following are not explicit permissions, but are implied by RECEIVE_MESSAGE and REPLYTO_MESSAGE and the scopes into which the bots can be used, declared in the manifest:</span></span>
 
    - <span data-ttu-id="b7a94-144">RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</span><span class="sxs-lookup"><span data-stu-id="b7a94-144">RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</span></span>
    - <span data-ttu-id="b7a94-145">RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT</span><span class="sxs-lookup"><span data-stu-id="b7a94-145">RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT</span></span>
    - <span data-ttu-id="b7a94-146">RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</span><span class="sxs-lookup"><span data-stu-id="b7a94-146">RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</span></span>

- <span data-ttu-id="b7a94-147">SEND_FILES, RECEIVE_FILES. <sup>2</sup> steuert, ob ein bot Dateien im persönlichen Chat senden und empfangen kann (noch nicht für Gruppen-Chats oder Kanäle unterstützt).</span><span class="sxs-lookup"><span data-stu-id="b7a94-147">SEND_FILES, RECEIVE_FILES.<sup>2</sup> Controls whether a bot can send and receive files in personal chat (not yet supported for group chat or channels).</span></span>

### <a name="considerations"></a><span data-ttu-id="b7a94-148">Überlegungen</span><span class="sxs-lookup"><span data-stu-id="b7a94-148">Considerations</span></span>

- <span data-ttu-id="b7a94-149">Bots haben nur Zugriff auf Teams, denen Sie hinzugefügt wurden, oder auf Benutzer, die Sie installiert haben.</span><span class="sxs-lookup"><span data-stu-id="b7a94-149">Bots only have access to teams to which they've been added or to users who have installed them.</span></span>

- <span data-ttu-id="b7a94-150">Bots empfangen nur Nachrichten, in denen Sie von den Benutzern ausdrücklich erwähnt werden.</span><span class="sxs-lookup"><span data-stu-id="b7a94-150">Bots only receive messages in which they're explicitly mentioned by users.</span></span> <span data-ttu-id="b7a94-151">Diese Daten verlassen das Unternehmensnetzwerk.</span><span class="sxs-lookup"><span data-stu-id="b7a94-151">This data leaves the corporate network.</span></span>

- <span data-ttu-id="b7a94-152">Bots können nur auf Unterhaltungen Antworten, in denen Sie erwähnt werden.</span><span class="sxs-lookup"><span data-stu-id="b7a94-152">Bots can only reply to conversations in which they're mentioned.</span></span>

- <span data-ttu-id="b7a94-153">Nachdem ein Nutzer sich mit einem bot unterhalten hat, kann er, wenn der bot die ID des Nutzers speichert, diesen Nutzer jederzeit direkt Nachrichten senden.</span><span class="sxs-lookup"><span data-stu-id="b7a94-153">After a user has conversed with a bot, if the bot stores that user's ID, it can send that user direct messages at any time.</span></span>

- <span data-ttu-id="b7a94-154">Es ist theoretisch möglich, dass bot-Nachrichten Links zu Phishing-oder Malware-Websites enthalten, aber Bots können vom Benutzer, dem mandantenadministrator oder Global von Microsoft blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="b7a94-154">It is theoretically possible for bot messages to contain links to phishing or malware sites, but bots can be blocked by the user, the tenant admin, or globally by Microsoft.</span></span>

- <span data-ttu-id="b7a94-155">Ein Bot kann sehr einfache Identitätsinformationen für die Teammitglieder, denen die app hinzugefügt wurde, oder für einzelne Benutzer in persönlichen oder Gruppen-Chats abrufen (und möglicherweise speichern).</span><span class="sxs-lookup"><span data-stu-id="b7a94-155">A bot can retrieve (and might store) very basic identity information for the team members the app has been added to, or for individual users in personal or group chats.</span></span> <span data-ttu-id="b7a94-156">Wenn Sie weitere Informationen zu diesen Benutzern erhalten möchten, muss der bot die Anmeldung bei Azure Active Directory (Azure AD) anfordern.</span><span class="sxs-lookup"><span data-stu-id="b7a94-156">To get further information about these users, the bot must require them to sign in to Azure Active Directory (Azure AD)</span></span>

- <span data-ttu-id="b7a94-157">Bots können die Liste der Kanäle in einem Team abrufen (und möglicherweise speichern). Diese Daten verlassen das Unternehmensnetzwerk.</span><span class="sxs-lookup"><span data-stu-id="b7a94-157">Bots can retrieve (and might store) the list of channels in a team; this data leaves the corporate network.</span></span>

- <span data-ttu-id="b7a94-158">Wenn eine Datei an einen bot gesendet wird, verlässt die Datei das Unternehmensnetzwerk.</span><span class="sxs-lookup"><span data-stu-id="b7a94-158">When a file is sent to a bot, the file leaves the corporate network.</span></span> <span data-ttu-id="b7a94-159">Für das Senden und empfangen von Dateien ist die Benutzergenehmigung für jede Datei erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b7a94-159">Sending and receiving files requires user approval for each file.</span></span> 

- <span data-ttu-id="b7a94-160">Standardmäßig sind Bots nicht in der Lage, im Namen des Benutzers zu agieren, aber Bots können Nutzer bitten, sich anzumelden. Sobald sich der Benutzer anmeldet, verfügt der bot über ein Zugriffstoken, mit dem er zusätzliche Aufgaben ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="b7a94-160">By default, bots don't have the ability to act on behalf of the user, but bots can ask users to sign in; as soon as the user signs in, the bot will have an access token with which it can do additional things.</span></span> <span data-ttu-id="b7a94-161">Genau das, was diese zusätzlichen Dinge sind, hängt vom bot ab und von der Stelle, an der sich der Benutzer anmeldet: https://apps.dev.microsoft.com/ ein Bot ist eine Azure AD-App, die bei registriert ist und über einen eigenen Satz von Berechtigungen verfügen kann.</span><span class="sxs-lookup"><span data-stu-id="b7a94-161">Exactly what those additional things are depends on the bot and where the user signs in: a bot is an Azure AD app registered at https://apps.dev.microsoft.com/ and can have its own set of permissions.</span></span>

- <span data-ttu-id="b7a94-162">Bots werden benachrichtigt, wenn Benutzer zu einem Team hinzugefügt oder daraus gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="b7a94-162">Bots are informed whenever users are added to or deleted from a team.</span></span>

- <span data-ttu-id="b7a94-163">Für Bots werden die IP-Adressen der Benutzer oder andere Verweisinformationen nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b7a94-163">Bots don't see users' IP addresses or other referrer information.</span></span> <span data-ttu-id="b7a94-164">Alle Informationen stammen von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b7a94-164">All information comes from Microsoft.</span></span> <span data-ttu-id="b7a94-165">(Es gibt eine Ausnahme: Wenn ein bot seine eigene Anmelde Erfahrung implementiert, werden die IP-Adressen und Verweisinformationen der Benutzer auf der Anmelde-UI angezeigt.)</span><span class="sxs-lookup"><span data-stu-id="b7a94-165">(There is one exception: if a bot implements its own sign-in experience, the sign-in UI will see users' IP addresses and referrer information.)</span></span>

- <span data-ttu-id="b7a94-166">Messaging-Erweiterungen hingegen sehen die IP-Adressen und Verweisinformationen von Benutzern.</span><span class="sxs-lookup"><span data-stu-id="b7a94-166">Messaging extensions, on the other hand, do see users' IP addresses and referrer information.</span></span>

- <span data-ttu-id="b7a94-167">App-Richtlinien (und unser AppSource-Überprüfungsprozess) erfordern Diskretion beim Posten persönlicher Chatnachrichten an Benutzer (über die POST_MESSAGE_TEAM-Berechtigung) für gültige Zwecke.</span><span class="sxs-lookup"><span data-stu-id="b7a94-167">App guidelines (and our AppSource review process) require discretion in posting personal chat messages to users (via the POST_MESSAGE_TEAM permission) for valid purposes.</span></span> <span data-ttu-id="b7a94-168">Im Fall von Missbrauch können Benutzer den bot blockieren, mandantenadministratoren können die APP blockieren, und Microsoft kann Bots bei Bedarf zentral blockieren.</span><span class="sxs-lookup"><span data-stu-id="b7a94-168">In the event of abuse, users can block the bot, tenant admins can block the app, and Microsoft can block bots centrally if necessary.</span></span>

<span data-ttu-id="b7a94-169"><sup>1</sup> einige Bots senden nur Nachrichten (POST_MESSAGE_USER).</span><span class="sxs-lookup"><span data-stu-id="b7a94-169"><sup>1</sup> Some bots only send messages (POST_MESSAGE_USER).</span></span> <span data-ttu-id="b7a94-170">Sie werden als "Benachrichtigungs-only"-Bots bezeichnet, aber der Ausdruck bezieht sich nicht auf das, was ein bot erlaubt oder nicht erlaubt, was bedeutet, dass der bot keine Konversations Erfahrung machen möchte.</span><span class="sxs-lookup"><span data-stu-id="b7a94-170">They're called "notification-only" bots, but the term doesn't refer to what a bot is allowed or not allowed to do, it means that the bot doesn't want to expose a conversational experience.</span></span> <span data-ttu-id="b7a94-171">Teams verwendet dieses Feld, um Funktionen in der UI zu deaktivieren, die normalerweise aktiviert werden. der Bot ist nicht eingeschränkt in dem, was er zu tun hat, im Vergleich zu Bots, die eine Konversations Erfahrung machen.</span><span class="sxs-lookup"><span data-stu-id="b7a94-171">Teams uses this field to disable functionality in the UI that would ordinarily be enabled; the bot isn't restricted in what it's allowed to do compared to bots that do expose a conversational experience.</span></span>

<span data-ttu-id="b7a94-172"><sup>2</sup> unterliegt der supportsFiles-booleschen Eigenschaft für das bot-Objekt in der Manifest. JSON-Datei für die app.</span><span class="sxs-lookup"><span data-stu-id="b7a94-172"><sup>2</sup> Governed by the supportsFiles Boolean property on the bot object in the manifest.json file for the app.</span></span>

> [!NOTE]
> <span data-ttu-id="b7a94-173">Wenn ein bot eine eigene Anmeldung hat, gibt es eine zweite – anders – Zustimmungs Erfahrung, wenn sich der Benutzer zum ersten Mal anmeldet.</span><span class="sxs-lookup"><span data-stu-id="b7a94-173">If a bot has its own sign-in, there's a second—different—consent experience the first time the user signs in.</span></span>
>
><span data-ttu-id="b7a94-174">Derzeit sind die Azure AD-Berechtigungen, die einer der Funktionen in einer Teams-app (bot-, Tab-, Connector-oder Messaging-Erweiterung) zugeordnet sind, vollständig von den hier aufgelisteten Teams-Berechtigungen getrennt.</span><span class="sxs-lookup"><span data-stu-id="b7a94-174">Currently, the Azure AD permissions associated with any of the capabilities inside a Teams app (bot, tab, connector, or messaging extension) are completely separate from the Teams permissions listed here.</span></span>

## <a name="tabs"></a><span data-ttu-id="b7a94-175">Registerkarten</span><span class="sxs-lookup"><span data-stu-id="b7a94-175">Tabs</span></span>

<span data-ttu-id="b7a94-176">Eine Registerkarte ist eine Website, die innerhalb von Teams ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b7a94-176">A tab is a website running inside Teams.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="b7a94-177">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="b7a94-177">Required permissions</span></span>

<span data-ttu-id="b7a94-178">SEND_AND_RECEIVE_WEB_DATA</span><span class="sxs-lookup"><span data-stu-id="b7a94-178">SEND_AND_RECEIVE_WEB_DATA</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="b7a94-179">Optionale Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="b7a94-179">Optional permissions</span></span>

<span data-ttu-id="b7a94-180">Keine (derzeit)</span><span class="sxs-lookup"><span data-stu-id="b7a94-180">None (currently)</span></span>

### <a name="considerations"></a><span data-ttu-id="b7a94-181">Überlegungen</span><span class="sxs-lookup"><span data-stu-id="b7a94-181">Considerations</span></span>

- <span data-ttu-id="b7a94-182">Das Risikoprofil einer Registerkarte ist nahezu identisch mit der Website, die auf einer Browserregister Karte ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b7a94-182">The risk profile for a tab is almost identical to that same website running in a browser tab.</span></span> 

- <span data-ttu-id="b7a94-183">Eine Registerkarte ruft auch den Kontext ab, in dem Sie ausgeführt wird, einschließlich des Anmeldenamens und des UPN des aktuellen Benutzers, der Azure AD-Objekt-ID für den aktuellen Benutzer, der ID der Office 365-Gruppe, in der Sie sich befindet (sofern es sich um ein Team handelt), der Mandanten-ID. und das aktuelle Gebietsschema des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="b7a94-183">A tab also gets the context in which it's running, including the sign-in name and UPN of the current user, the Azure AD Object ID for the current user, the ID of the Office 365 Group in which it resides (if it's a team), the tenant ID, and the current locale of the user.</span></span> <span data-ttu-id="b7a94-184">Damit diese IDs jedoch den Informationen eines Benutzers zugeordnet werden können, muss sich der Benutzer bei Azure AD anmelden.</span><span class="sxs-lookup"><span data-stu-id="b7a94-184">However, to map these IDs to a user's information, the tab would have to make the user sign in to Azure AD.</span></span>

## <a name="connectors"></a><span data-ttu-id="b7a94-185">Verbinder</span><span class="sxs-lookup"><span data-stu-id="b7a94-185">Connectors</span></span>

<span data-ttu-id="b7a94-186">Ein Connector Bucht Nachrichten in einem Kanal, wenn Ereignisse in einem externen System auftreten.</span><span class="sxs-lookup"><span data-stu-id="b7a94-186">A connector posts messages to a channel when events in an external system occur.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="b7a94-187">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="b7a94-187">Required permissions</span></span>

<span data-ttu-id="b7a94-188">POST_MESSAGE_CHANNEL</span><span class="sxs-lookup"><span data-stu-id="b7a94-188">POST_MESSAGE_CHANNEL</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="b7a94-189">Optionale Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="b7a94-189">Optional permissions</span></span>

<span data-ttu-id="b7a94-190">REPLYTO_CONNECTOR_MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="b7a94-190">REPLYTO_CONNECTOR_MESSAGE.</span></span> <span data-ttu-id="b7a94-191">Bestimmte Connectors unterstützen umsetzbare Nachrichten, mit denen Benutzer gezielte Antworten auf die Connector-Nachricht senden können, beispielsweisedurch Hinzufügen einer Antwort auf ein GitHub-Problem oder durch Hinzufügen eines Datums zu einer Trello-Karte.</span><span class="sxs-lookup"><span data-stu-id="b7a94-191">Certain connectors support actionable messages, which allow users to post targeted replies to the connector message, for example by adding a response to a GitHub issue or adding a date to a Trello card.</span></span>

### <a name="considerations"></a><span data-ttu-id="b7a94-192">Überlegungen</span><span class="sxs-lookup"><span data-stu-id="b7a94-192">Considerations</span></span>

- <span data-ttu-id="b7a94-193">Das System, in dem Connector-Nachrichten gepostet werden, weiß nicht, wer die Nachricht sendet oder wer die Nachrichten empfängt: Es werden keine Informationen über den Empfänger veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="b7a94-193">The system that posts connector messages doesn't know who it's posting to or who receives the messages: no information about the recipient is disclosed.</span></span> <span data-ttu-id="b7a94-194">(Microsoft ist der tatsächliche Empfänger, nicht der Mandant; Microsoft führt den eigentlichen Beitrag für den Kanal aus.)</span><span class="sxs-lookup"><span data-stu-id="b7a94-194">(Microsoft is the actual recipient, not the tenant; Microsoft does the actual post to the channel.)</span></span>

- <span data-ttu-id="b7a94-195">Keine Daten verlassen das Unternehmensnetzwerk, wenn Connector-Nachrichten in einem Kanal bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="b7a94-195">No data leaves the corporate network when connector messages are posted to a channel.</span></span>

- <span data-ttu-id="b7a94-196">Connectors, die umsetzbare Nachrichten (REPLYTO_CONNECTOR_MESSAGE Berechtigung) unterstützen, sehen auch keine IP-Adressen-und Verweisinformationen; Diese Informationen werden an Microsoft gesendet und dann an HTTP-Endpunkte weitergeleitet, die zuvor bei Microsoft im Connectors-Portal registriert wurden.</span><span class="sxs-lookup"><span data-stu-id="b7a94-196">Connectors that support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission) also don't see IP address and referrer information; this information is sent to Microsoft and then routed to HTTP endpoints that were previously registered with Microsoft in the Connectors portal.</span></span>

- <span data-ttu-id="b7a94-197">Jedes Mal, wenn ein Connector für einen Kanal konfiguriert ist, wird eine eindeutige URL für diese Connector-Instanz erstellt.</span><span class="sxs-lookup"><span data-stu-id="b7a94-197">Each time a connector is configured for a channel, a unique URL for that connector instance is created.</span></span> <span data-ttu-id="b7a94-198">Wenn diese Connector-Instanz gelöscht wird, kann die URL nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b7a94-198">If that connector instance is deleted, the URL can no longer be used.</span></span>

- <span data-ttu-id="b7a94-199">Connector-Nachrichten können keine Dateianlagen enthalten.</span><span class="sxs-lookup"><span data-stu-id="b7a94-199">Connector messages can't contain file attachments.</span></span>

- <span data-ttu-id="b7a94-200">Die URL der Connector-Instanz sollte als geheim/vertraulich behandelt werden: jede Person, die über diese URL verfügt, kann Sie wie eine e-Mail-Adresse Posten.</span><span class="sxs-lookup"><span data-stu-id="b7a94-200">The connector instance URL should be treated as secret/confidential: anyone who has that URL can post to it, like an email address.</span></span> <span data-ttu-id="b7a94-201">Daher besteht ein gewisses Risiko von Spam oder Links zu Phishing-oder Malware-Websites.</span><span class="sxs-lookup"><span data-stu-id="b7a94-201">Therefore, there's some risk of spam or links to phishing or malware sites.</span></span> <span data-ttu-id="b7a94-202">In diesem Fall können Teambesitzer die Connector-Instanz löschen.</span><span class="sxs-lookup"><span data-stu-id="b7a94-202">If that were to happen, team owners can delete the connector instance.</span></span>

- <span data-ttu-id="b7a94-203">Wenn der Dienst, der Connector-Nachrichten sendet, kompromittiert wurde und mit dem Senden von Spam/Phishing/Malware-Links beginnt, kann ein mandantenadministrator verhindern, dass neue Connector-Instanzen erstellt werden, und Microsoft kann Sie zentral blockieren.</span><span class="sxs-lookup"><span data-stu-id="b7a94-203">If the service that sends connector messages were to become compromised and start sending spam/phishing/malware links, a tenant administrator can prevent new connector instances from being created and Microsoft can block them centrally.</span></span>

> [!NOTE]
> <span data-ttu-id="b7a94-204">Es ist derzeit nicht möglich zu wissen, welche Connectors umsetzbare Nachrichten (REPLYTO_CONNECTOR_MESSAGE Berechtigung) unterstützen.</span><span class="sxs-lookup"><span data-stu-id="b7a94-204">It's not currently possible to know which connectors support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission).</span></span>

## <a name="outgoing-webhooks"></a><span data-ttu-id="b7a94-205">Ausgehende webhooks</span><span class="sxs-lookup"><span data-stu-id="b7a94-205">Outgoing webhooks</span></span>

<span data-ttu-id="b7a94-206">*Ausgehende webhooks* werden von Teambesitzern oder Teammitgliedern im Handumdrehen erstellt.</span><span class="sxs-lookup"><span data-stu-id="b7a94-206">*Outgoing webhooks* are created on the fly by team owners or team members.</span></span> <span data-ttu-id="b7a94-207">Sie sind keine Funktionen von Teams-apps; Diese Informationen sind zur Vollständigkeit enthalten.</span><span class="sxs-lookup"><span data-stu-id="b7a94-207">They aren't capabilities of Teams apps; this information is included for completeness.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="b7a94-208">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="b7a94-208">Required permissions</span></span>

<span data-ttu-id="b7a94-209">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="b7a94-209">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="b7a94-210">Kann Nachrichten von Benutzern empfangen und darauf antworten.</span><span class="sxs-lookup"><span data-stu-id="b7a94-210">Can receive messages from users and reply to them.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="b7a94-211">Optionale Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="b7a94-211">Optional permissions</span></span>

<span data-ttu-id="b7a94-212">Keine</span><span class="sxs-lookup"><span data-stu-id="b7a94-212">None</span></span>

### <a name="considerations"></a><span data-ttu-id="b7a94-213">Überlegungen</span><span class="sxs-lookup"><span data-stu-id="b7a94-213">Considerations</span></span>

- <span data-ttu-id="b7a94-214">Ausgehende webhooks ähneln Bots, haben aber weniger Privilegien.</span><span class="sxs-lookup"><span data-stu-id="b7a94-214">Outgoing webhooks are similar to bots but have fewer privileges.</span></span> <span data-ttu-id="b7a94-215">Sie müssen ausdrücklich erwähnt werden, genau wie Bots.</span><span class="sxs-lookup"><span data-stu-id="b7a94-215">They must be explicitly mentioned, just like bots.</span></span>

- <span data-ttu-id="b7a94-216">Beim Registrieren eines ausgehenden webhooks wird ein geheimer Schlüssel generiert, der dem ausgehenden webhook ermöglicht, zu überprüfen, ob der Absender Microsoft Teams im Gegensatz zu einem böswilligen Angreifer ist.</span><span class="sxs-lookup"><span data-stu-id="b7a94-216">When an outgoing webhook is registered, a secret is generated, which allows the outgoing webhook to verify that the sender is Microsoft Teams as opposed to a malicious attacker.</span></span> <span data-ttu-id="b7a94-217">Dieses Geheimnis sollte geheim bleiben; Jeder Benutzer, der Zugriff darauf hat, kann die Identität von Microsoft Teams einsehen.</span><span class="sxs-lookup"><span data-stu-id="b7a94-217">This secret should remain a secret; anyone who has access to it can impersonate Microsoft Teams.</span></span> <span data-ttu-id="b7a94-218">Wenn das Geheimnis beeinträchtigt wird, kann der ausgehende webhook gelöscht und neu erstellt werden, und es wird ein neuer Schlüssel generiert.</span><span class="sxs-lookup"><span data-stu-id="b7a94-218">If the secret is compromised, the outgoing webhook can be deleted and re-created, and a new secret will be generated.</span></span>

- <span data-ttu-id="b7a94-219">Obwohl es möglich ist, einen ausgehenden webhook zu erstellen, der den geheimen Schlüssel nicht überprüft, empfehlen wir dafür.</span><span class="sxs-lookup"><span data-stu-id="b7a94-219">Although it's possible to create an outgoing webhook that doesn't validate the secret, we recommend against it.</span></span>

- <span data-ttu-id="b7a94-220">Anders als das empfangen und beantworten von Nachrichten können ausgehende webhooks nicht viel tun: Sie können keine proaktiven Nachrichten senden, Sie können keine Dateien senden oder empfangen, Sie können nichts anderes tun, was Bots tun können, außer zu empfangen und auf Nachrichten zu antworten.</span><span class="sxs-lookup"><span data-stu-id="b7a94-220">Other than receiving and replying to messages, outgoing webhooks can't do much: they can't proactively send messages, they can't send or receive files, they can't do anything else that bots can do except receive and reply to messages.</span></span>
