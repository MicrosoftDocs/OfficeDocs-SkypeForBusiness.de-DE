---
title: Exportieren von Inhalten mit den Microsoft Teams Export-APIs
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: In diesem Artikel erfahren Sie, wie Sie Team Inhalte mithilfe der Microsoft Teams-Export-APIs exportieren können.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 896e60e8de6e01208a07c40e757a79a12192383a
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611819"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a><span data-ttu-id="cf236-103">Exportieren von Inhalten mit den Microsoft Teams Export-APIs</span><span class="sxs-lookup"><span data-stu-id="cf236-103">Export content with the Microsoft Teams Export APIs</span></span>

<span data-ttu-id="cf236-104">Teams-Export-APIs ermöglichen es Ihnen, 1:1-und Gruppen-Chatnachrichten aus Microsoft Teams zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="cf236-104">Teams Export APIs allow you to export 1:1 and group chat messages from Microsoft Teams.</span></span> <span data-ttu-id="cf236-105">Wenn Ihre Organisation Microsoft Teams-Nachrichten exportieren muss, können Sie diese mithilfe von Team Export-APIs extrahieren.</span><span class="sxs-lookup"><span data-stu-id="cf236-105">If your organization needs to export Microsoft Teams messages, you are able to extract them using Teams Export APIs.</span></span> <span data-ttu-id="cf236-106">*Chat-Nachricht* stellt eine einzelne Chatnachricht in einem [Kanal](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) oder [Chat](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta)dar.</span><span class="sxs-lookup"><span data-stu-id="cf236-106">*Chat Message* represents an individual chat message within a [channel](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) or [chat](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta).</span></span> <span data-ttu-id="cf236-107">Bei der Chatnachricht kann es sich um eine root-Chatnachricht oder einen Teil eines Antwort Threads handeln, der durch die **replyToId** -Eigenschaft in der Chatnachricht definiert ist.</span><span class="sxs-lookup"><span data-stu-id="cf236-107">The chat message can be a root chat message or part of a reply thread that is defined by the **replyToId** property in the chat message.</span></span>

<span data-ttu-id="cf236-108">Nachfolgend finden Sie einige Beispiele, wie Sie diese Export-APIs verwenden können:</span><span class="sxs-lookup"><span data-stu-id="cf236-108">Here are some examples on how you can use these export APIs:</span></span>

- <span data-ttu-id="cf236-109">**Beispiel 1**: Wenn Sie Microsoft Teams in Ihrer Organisation aktiviert haben und alle Microsoft Teams-Nachrichten bis dato programmgesteuert exportieren möchten, indem Sie den Datumsbereich für einen bestimmten Benutzer übergeben.</span><span class="sxs-lookup"><span data-stu-id="cf236-109">**Example 1**: If you have enabled Microsoft Teams in your organization and want to export all the Microsoft Teams messages to date programmatically by passing the date range for a given user.</span></span>
- <span data-ttu-id="cf236-110">**Beispiel 2**: Wenn Sie alle Benutzer Nachrichten programmgesteuert exportieren möchten, indem Sie einen Datumsbereich angeben.</span><span class="sxs-lookup"><span data-stu-id="cf236-110">**Example 2**: If you want to programmatically export all user messages daily by providing a date range.</span></span> <span data-ttu-id="cf236-111">Export-APIs können alle Nachrichten abrufen, die während des angegebenen Datumsbereichs erstellt oder aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="cf236-111">Export APIs can retrieve all the messages created or updated during the given date range.</span></span>

## <a name="what-is-supported-by-the-teams-export-apis"></a><span data-ttu-id="cf236-112">Was wird von den Export-APIs für Teams unterstützt?</span><span class="sxs-lookup"><span data-stu-id="cf236-112">What is supported by the Teams Export APIs?</span></span>

- <span data-ttu-id="cf236-113">**Massen Export der Teams-Nachricht:** Teams-Export-APIs unterstützen bis zu 200 RPS pro App pro Mandant und 600 RPS für eine Anwendung, mit diesen Einschränkungen sollten Sie in der Lage sein, den Massen Export von Teams-Nachrichten auszuführen.</span><span class="sxs-lookup"><span data-stu-id="cf236-113">**Bulk Export of Teams Message:** Teams Export APIs support up to 200 RPS Per App Per tenant and 600 RPS for an Application, with these limits you should be able to bulk export of Teams messages.</span></span>
- <span data-ttu-id="cf236-114">**Anwendungskontext**: zum Aufrufen von Microsoft Graph muss Ihre APP ein Zugriffstoken von der Microsoft Identity-Plattform erwerben.</span><span class="sxs-lookup"><span data-stu-id="cf236-114">**Application Context**: To call Microsoft Graph, your app must acquire an access token from the Microsoft identity platform.</span></span> <span data-ttu-id="cf236-115">Das Zugriffstoken enthält Informationen über Ihre APP und die Berechtigungen für die Ressourcen und APIs, die über Microsoft Graph zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="cf236-115">The access token contains information about your app and the permissions it has for the resources and APIs available through Microsoft Graph.</span></span> <span data-ttu-id="cf236-116">Zum Abrufen eines Zugriffstokens muss Ihre APP bei der Microsoft Identity-Plattform registriert und von einem Benutzer oder Administrator für den Zugriff auf die benötigten Microsoft Graph-Ressourcen autorisiert werden.</span><span class="sxs-lookup"><span data-stu-id="cf236-116">To get an access token, your app must be registered with the Microsoft identity platform and be authorized by either a user or an administrator for access to the Microsoft Graph resources it needs.</span></span>

    <span data-ttu-id="cf236-117">Wenn Sie bereits mit der Integration einer APP mit der Microsoft Identity-Plattform zum Abrufen von Token vertraut sind, lesen Sie den Abschnitt [Nächste Schritte](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) für Informationen und Beispiele für Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="cf236-117">If you are already familiar with integrating an app with the Microsoft identity platform to get tokens, see the [Next Steps](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) section for information and samples specific to Microsoft Graph.</span></span>
- <span data-ttu-id="cf236-118">**Hybrid Umgebung:** Export-APIs unterstützen Nachrichten, die von Benutzern gesendet werden, die in einer Hybrid Umgebung bereitgestellt werden (Lokales Exchange und Teams).</span><span class="sxs-lookup"><span data-stu-id="cf236-118">**Hybrid Environment:** Export APIs support messages sent by users who are provisioned on Hybrid Environment (on-premises Exchange and Teams).</span></span> <span data-ttu-id="cf236-119">Alle Nachrichten, die von Benutzern gesendet werden, die für eine Hybridumgebung konfiguriert sind, können mithilfe von Export-APIs aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="cf236-119">Any messages that are sent by users who are configured for hybrid environment will be accessible using Export APIs.</span></span>
- <span data-ttu-id="cf236-120">**Gelöschte Nachrichten des Benutzers:** Nachrichten, die vom Benutzer des Teams-Clients gelöscht werden, können mithilfe von Export-APIs bis zu 30 Tage nach dem Löschvorgang aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="cf236-120">**User Deleted Messages:** Messages that are deleted by user from Teams client can be accessed using export APIs up to 30 days from the time of deletion.</span></span>
- <span data-ttu-id="cf236-121">**Nachrichtenanlagen:** Export-APIs enthalten die Links zu den Anlagen, die als Teil von Nachrichten gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="cf236-121">**Message Attachments:** Export APIs include the links to the attachments that are sent as part of messages.</span></span> <span data-ttu-id="cf236-122">Mit Export-APIs können Sie die in den Nachrichten angefügten Dateien abrufen.</span><span class="sxs-lookup"><span data-stu-id="cf236-122">Using Export APIs you can retrieve the files attached in the messages.</span></span>
- <span data-ttu-id="cf236-123">**Eigenschaften von Chat Nachrichten:** Weitere Informationen finden Sie in der vollständigen Liste der Eigenschaften, die Team- [APIs unterstützen](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties).</span><span class="sxs-lookup"><span data-stu-id="cf236-123">**Chat Message Properties:** Refer to the complete list of properties that Teams Export APIs support [here](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties).</span></span>

## <a name="how-to-access-teams-export-apis"></a><span data-ttu-id="cf236-124">Zugreifen auf Team Export-APIs</span><span class="sxs-lookup"><span data-stu-id="cf236-124">How to access Teams Export APIs</span></span>

- <span data-ttu-id="cf236-125">**Beispiel 1** ist eine einfache Abfrage, mit der alle Nachrichten eines Benutzers ohne Filter abgerufen werden:</span><span class="sxs-lookup"><span data-stu-id="cf236-125">**Example 1** is a simple query to retrieve all the messages of a user without any filters:</span></span>

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages
    ```

- <span data-ttu-id="cf236-126">**Beispiel 2** ist eine Beispielabfrage, um alle Nachrichten eines Benutzers abzurufen, indem Datums Zeitfilter und Top 50-Nachrichten angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="cf236-126">**Example 2** is a sample query to retrieve all the messages of a user by specifying date time filters and top 50 messages:</span></span>

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```

>[!NOTE]
><span data-ttu-id="cf236-127">Die API gibt die Antwort mit dem Link "Nächste Seite" zurück, falls mehrere Ergebnisse vorliegen.</span><span class="sxs-lookup"><span data-stu-id="cf236-127">The API returns response with next page link in case of multiple results.</span></span> <span data-ttu-id="cf236-128">Wenn Sie den nächsten Satz von Ergebnissen erhalten möchten, rufen Sie einfach die URL von @odata. Nextlink.</span><span class="sxs-lookup"><span data-stu-id="cf236-128">For getting next set of results, simply call GET on the url from @odata.nextlink.</span></span> <span data-ttu-id="cf236-129">Wenn @odata. Nextlink nicht vorhanden oder NULL ist, werden alle Nachrichten abgerufen.</span><span class="sxs-lookup"><span data-stu-id="cf236-129">If @odata.nextlink is not present or null then all messages are retrieved.</span></span>

## <a name="prerequisites-to-access-teams-export-apis"></a><span data-ttu-id="cf236-130">Voraussetzungen für den Zugriff auf Team Export-APIs</span><span class="sxs-lookup"><span data-stu-id="cf236-130">Prerequisites to access Teams Export APIs</span></span> 

- <span data-ttu-id="cf236-131">Die Export-APIs für Teams befinden sich derzeit in der Vorschau.</span><span class="sxs-lookup"><span data-stu-id="cf236-131">Teams Export APIs are currently in preview.</span></span> <span data-ttu-id="cf236-132">Es steht Benutzern und Mandanten nur zur Verfügung, die über die [erforderlichen Lizenzen](https://aka.ms/teams-changenotification-licenses) für APIs verfügen.</span><span class="sxs-lookup"><span data-stu-id="cf236-132">It will only be available to users and tenants that have the [required licenses](https://aka.ms/teams-changenotification-licenses) for APIs.</span></span> <span data-ttu-id="cf236-133">In Zukunft kann Microsoft verlangen, dass Sie oder Ihre Kunden zusätzliche Gebühren auf der Grundlage der Datenmenge Zahlen, auf die über die API zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="cf236-133">In the future, Microsoft may require you or your customers to pay additional fees based on the amount of data accessed through the API.</span></span>
- <span data-ttu-id="cf236-134">Microsoft Teams-APIs in Microsoft Graph, die auf vertrauliche Daten zugreifen, gelten als geschützte APIs.</span><span class="sxs-lookup"><span data-stu-id="cf236-134">Microsoft Teams APIs in Microsoft Graph that access sensitive data are considered protected APIs.</span></span> <span data-ttu-id="cf236-135">Für Export-APIs ist es erforderlich, dass Sie über Berechtigungen und Zustimmung hinaus zusätzliche Überprüfung haben, bevor Sie Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="cf236-135">Export APIs require that you have additional validation, beyond permissions and consent, before you can use them.</span></span> <span data-ttu-id="cf236-136">Wenn Sie den Zugriff auf diese geschützten APIs anfordern möchten, füllen Sie das [Anforderungsformular](https://aka.ms/teamsgraph/requestaccess)aus.</span><span class="sxs-lookup"><span data-stu-id="cf236-136">To request access to these protected APIs, complete the [request form](https://aka.ms/teamsgraph/requestaccess).</span></span>
- <span data-ttu-id="cf236-137">Anwendungsberechtigungen werden von apps verwendet, die ohne angemeldeten Benutzer ausgeführt werden. Anwendungsberechtigungen können nur von einem Administrator zugestimmt werden.</span><span class="sxs-lookup"><span data-stu-id="cf236-137">Application permissions are used by apps that run without a signed-in user present; application permissions can only be consented by an administrator.</span></span> <span data-ttu-id="cf236-138">Die folgenden Berechtigungen sind erforderlich:</span><span class="sxs-lookup"><span data-stu-id="cf236-138">The following permissions are needed:</span></span>

    - <span data-ttu-id="cf236-139">*Chat. Read. all*: ermöglicht den Zugriff auf alle 1:1-und Gruppen-Chatnachrichten</span><span class="sxs-lookup"><span data-stu-id="cf236-139">*Chat.Read.All*: enables access to all 1:1 and Group chat messages</span></span> 
    - <span data-ttu-id="cf236-140">*User. Read. all*: ermöglicht den Zugriff auf die Liste der Benutzer für einen Mandanten</span><span class="sxs-lookup"><span data-stu-id="cf236-140">*User.Read.All*: enables access to the list of users for a tenant</span></span> 

## <a name="json-representation"></a><span data-ttu-id="cf236-141">JSON-Darstellung</span><span class="sxs-lookup"><span data-stu-id="cf236-141">JSON representation</span></span>

<span data-ttu-id="cf236-142">Im folgenden Beispiel handelt es sich um eine JSON-Darstellung der Ressource:</span><span class="sxs-lookup"><span data-stu-id="cf236-142">The following example is a JSON representation of the resource:</span></span>

<span data-ttu-id="cf236-143">Namespace: Microsoft. Graph</span><span class="sxs-lookup"><span data-stu-id="cf236-143">Namespace: microsoft.graph</span></span>

```JSON
{
"id": "string (identifier)",
"replyToId": "string (identifier)",
"from": {"@odata.type": "microsoft.graph.identitySet"},
"etag": "string",
"messageType": "string",
"createdDateTime": "string (timestamp)",
"lastModifiedDateTime": "string (timestamp)",
"deletedDateTime": "string (timestamp)",
"subject": "string",
"from": {
                "application": null,
                "device": null,
                "conversation": null,
                "user": {
                    "id": "string (identifier)",
                    "displayName": "string",
                    "userIdentityType": "aadUser"                }
            },
"body": {"@odata.type": "microsoft.graph.itemBody"},
"summary": "string",
"chatId": "string (identifier)"
"attachments": \[{"@odata.type": "microsoft.graph.chatMessageAttachment"}\],
"mentions": \[{"@odata.type": "microsoft.graph.chatMessageMention"}\],
"importance": "string",
"locale": "string",
}
```

>[!NOTE]
><span data-ttu-id="cf236-144">Weitere Informationen zur chatMessage-Ressource finden Sie im Artikel zum [chatMessage-Ressourcentyp](https://docs.microsoft.com/graph/api/resources/chatmessage) .</span><span class="sxs-lookup"><span data-stu-id="cf236-144">For more details on chatMessage resource, see the [chatMessage resource type](https://docs.microsoft.com/graph/api/resources/chatmessage) article.</span></span>
