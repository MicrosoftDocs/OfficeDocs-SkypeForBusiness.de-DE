---
title: Konfigurieren des Kompatibilitätsdienstes auf dem Server für beständigen Chat in Skype for Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24e36ea3-fb8a-45a4-b6b7-38c2e256b218
description: 'Zusammenfassung: Erfahren Sie, wie den Dienst Persistent Chat Server-Kompatibilität in Skype für Business Server 2015 zu konfigurieren.'
ms.openlocfilehash: 8d6fff09a59870c8550627bcf4222192e405c871
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375929"
---
# <a name="configure-the-compliance-service-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="4a3da-103">Konfigurieren des Kompatibilitätsdienstes auf dem Server für beständigen Chat in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4a3da-103">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>

<span data-ttu-id="4a3da-104">**Zusammenfassung:** Erfahren Sie, wie den Dienst Persistent Chat Server-Kompatibilität in Skype für Business Server 2015 zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4a3da-104">**Summary:** Learn how to configure the Persistent Chat Server Compliance service in Skype for Business Server 2015.</span></span>

<span data-ttu-id="4a3da-105">Dank der Konformität des beständigen Chats können Administratoren ein Archiv von Nachrichten des beständigen Chats und von Aktivitäten führen.</span><span class="sxs-lookup"><span data-stu-id="4a3da-105">Persistent Chat compliance lets administrators maintain an archive of Persistent Chat messages as well as activities.</span></span> <span data-ttu-id="4a3da-106">Die Einhaltung von Bestimmungen und archiviert Daten im Zusammenhang mit hergeschickt Persistent Chat Server, wenn ein Teilnehmer:</span><span class="sxs-lookup"><span data-stu-id="4a3da-106">The Compliance service records and archives data related to each Persistent Chat Server conversation, including when a participant:</span></span>

- <span data-ttu-id="4a3da-107">Verknüpft einen Raum beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="4a3da-107">Joins a Persistent Chat room</span></span>

- <span data-ttu-id="4a3da-108">Einen Chatroom verlässt</span><span class="sxs-lookup"><span data-stu-id="4a3da-108">Leaves a chat room</span></span>

- <span data-ttu-id="4a3da-109">Eine Nachricht veröffentlicht</span><span class="sxs-lookup"><span data-stu-id="4a3da-109">Posts a message</span></span>

- <span data-ttu-id="4a3da-110">Den Chatverlauf anzeigt</span><span class="sxs-lookup"><span data-stu-id="4a3da-110">Views chat history</span></span>

- <span data-ttu-id="4a3da-111">Eine Datei hochlädt</span><span class="sxs-lookup"><span data-stu-id="4a3da-111">Uploads a file</span></span>

- <span data-ttu-id="4a3da-112">Eine Datei herunterlädt</span><span class="sxs-lookup"><span data-stu-id="4a3da-112">Downloads a file</span></span>

<span data-ttu-id="4a3da-113">Diese Informationen können bei Bedarf von der SQL-Konformitätsdatenbank abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="4a3da-113">This information can be retrieved from the Compliance SQL database as needed.</span></span> 

> [!NOTE]
> <span data-ttu-id="4a3da-114">Beständiger Chat wird steht in Skype für Business Server 2015 jedoch nicht mehr unterstützt in Skype Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="4a3da-114">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="4a3da-115">Die gleiche Funktionalität ist in Teams verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4a3da-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="4a3da-116">Weitere Informationen finden Sie unter [Weg von Skype für Unternehmen, die Microsoft-Teams](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="4a3da-116">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="4a3da-117">Wenn Sie Persistent Chat verwenden müssen, sind Ihrer Auswahl an Benutzer, die diese Funktionalität Teams migrieren oder weiterhin Skype für Business Server 2015 verwenden.</span><span class="sxs-lookup"><span data-stu-id="4a3da-117">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="configure-the-compliance-service-by-using-windows-powershell"></a><span data-ttu-id="4a3da-118">Konfigurieren des Konformitätsdiensts mit Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a3da-118">Configure the Compliance service by using Windows PowerShell</span></span>

<span data-ttu-id="4a3da-119">Nachdem der Konformitätsdienst mithilfe des Topologie-Generators aktiviert wurde, können Sie den Dienst mit dem Cmdlet **Set-CsPersistenChatComplianceConfiguration** konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="4a3da-119">After the Compliance service has been enabled by using the Topology Builder, you can configure the service by using the **Set-CsPersistenChatComplianceConfiguration** cmdlet:</span></span>

```
Set-CsPersistentChatComplianceConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>
```

<span data-ttu-id="4a3da-120">oder</span><span class="sxs-lookup"><span data-stu-id="4a3da-120">or</span></span>

```
Set-CsPersistentChatComplianceConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>
```

<span data-ttu-id="4a3da-121">Sie können die folgenden Einstellungen konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="4a3da-121">You can set the following parameters:</span></span>

- <span data-ttu-id="4a3da-122">AdapterType: Zum Konfigurieren des Adaptertyps.</span><span class="sxs-lookup"><span data-stu-id="4a3da-122">AdapterType - Lets you specify the adapter type.</span></span> <span data-ttu-id="4a3da-123">Ein Adapter ist ein Produkt eines Drittanbieters, das die Daten in der Konformitätsdatenbank in ein spezielles Format konvertiert.</span><span class="sxs-lookup"><span data-stu-id="4a3da-123">An adapter is a third-party product that converts the data in the compliance database to a specific format.</span></span> <span data-ttu-id="4a3da-124">Das Standardformat ist XML.</span><span class="sxs-lookup"><span data-stu-id="4a3da-124">XML is the default.</span></span>

- <span data-ttu-id="4a3da-125">OneChatRoomPerOutputFile - dieser Parameter können Sie angeben, dass trennen, die Sie Berichte für jeden Chatroom erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="4a3da-125">OneChatRoomPerOutputFile - This parameter lets you specify that separate reports to be created for each chat room.</span></span>

- <span data-ttu-id="4a3da-126">AddChatRoomDetails: Wenn dieser Parameter aktiviert ist, werden zu jedem Chatroom in der Datenbank zusätzliche Details aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="4a3da-126">AddChatRoomDetails - When enabled, this parameter records additional details about each chat room in the database.</span></span> <span data-ttu-id="4a3da-127">Da sich die Größe der Datenbank durch diese Einstellung erheblich erhöhen kann, ist der Parameter standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="4a3da-127">Because this setting can greatly increase the size of the database, it is disabled by default.</span></span>

- <span data-ttu-id="4a3da-128">AddUserDetails: Wenn dieser Parameter aktiviert ist, werden für jeden Chatroom-Benutzer in der Datenbank zusätzliche Details aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="4a3da-128">AddUserDetails - When enabled, this parameter records additional details about each chat room user in the database.</span></span> <span data-ttu-id="4a3da-129">Da sich die Größe der Datenbank durch diese Einstellung erheblich erhöhen kann, ist der Parameter standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="4a3da-129">Because this setting can greatly increase the size of the database, it is disabled by default.</span></span>

- <span data-ttu-id="4a3da-130">Identity: Dieser Parameter ermöglicht das Festlegen von Konformitätseinstellungen für eine bestimmte Sammlung, z. B. auf globaler, Standort- und Serviceebene.</span><span class="sxs-lookup"><span data-stu-id="4a3da-130">Identity - This parameter allows compliance settings to be scoped for a particular collection, including the global, site, and service levels.</span></span> <span data-ttu-id="4a3da-131">Der Standardwert ist die globale Ebene.</span><span class="sxs-lookup"><span data-stu-id="4a3da-131">The default is the global level.</span></span> 

- <span data-ttu-id="4a3da-132">RunInterval: Dieser Parameter gibt die Zeitdauer an, bis der Server die nächste Konformitätsausgabedatei erstellt (der Standardwert ist 15 Minuten).</span><span class="sxs-lookup"><span data-stu-id="4a3da-132">RunInterval - This parameter dictates the amount of time before the server creates the next compliance output file (the default is 15 minutes).</span></span>

## <a name="use-a-customized-compliance-adapter"></a><span data-ttu-id="4a3da-133">Verwenden eines benutzerdefinierten Konformitätsadapters</span><span class="sxs-lookup"><span data-stu-id="4a3da-133">Use a customized compliance adapter</span></span>

<span data-ttu-id="4a3da-134">Sie können schreiben ein benutzerdefiniertes Adapters statt des XmlAdapter, die mit Persistent Chat Server installiert ist.</span><span class="sxs-lookup"><span data-stu-id="4a3da-134">You can write a custom adapter instead of using the XmlAdapter that is installed with Persistent Chat Server.</span></span> <span data-ttu-id="4a3da-135">Hierzu müssen Sie eine .NET Framework-Assembly bereitstellen, die eine öffentliche Klasse enthält, die die **IComplianceAdapter**-Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="4a3da-135">To accomplish this, you must provide a .NET Framework assembly that contains a public class that implements the **IComplianceAdapter** interface.</span></span> <span data-ttu-id="4a3da-136">Sie müssen diese Assembly im Installationsordner Persistent Chat Server der einzelnen Server in Ihrem Persistent Chat Server Pool platzieren.</span><span class="sxs-lookup"><span data-stu-id="4a3da-136">You must place this assembly in the Persistent Chat Server installation folder of each server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="4a3da-137">Jeder der Konformitätsserver kann Konformitätsdaten für Ihren Adapter bereitstellen, aber die Konformitätsserver stellen keine doppelten Konformitätsdaten für mehrere Instanzen des Adapters bereit.</span><span class="sxs-lookup"><span data-stu-id="4a3da-137">Any one of the Compliance servers can provide compliance data to your adapter, but the compliance servers will not provide duplicate compliance data to multiple instances of your adapter.</span></span>

<span data-ttu-id="4a3da-138">Die Schnittstelle ist in der Assembly Compliance.dll im Namespace definiert `Microsoft.Rtc.Internal.Chat.Server.Compliance`.</span><span class="sxs-lookup"><span data-stu-id="4a3da-138">The interface is defined in the Compliance.dll assembly in the namespace  `Microsoft.Rtc.Internal.Chat.Server.Compliance`.</span></span> <span data-ttu-id="4a3da-139">Die Schnittstelle definiert zwei Methoden, die Ihr benutzerdefinierter Adapter implementieren muss.</span><span class="sxs-lookup"><span data-stu-id="4a3da-139">The interface defines two methods that your custom adapter must implement.</span></span>

<span data-ttu-id="4a3da-140">Der beständigen Chat Kompatibilitätsserver wird die folgende Methode aufrufen, wenn der Adapter zum ersten Mal geladen.</span><span class="sxs-lookup"><span data-stu-id="4a3da-140">The Persistent Chat Compliance server will call the following method when the adapter first loads.</span></span> <span data-ttu-id="4a3da-141">Die `AdapterConfig` enthält den beständigen Chat Kompatibilitätskonfiguration, die für den kompatibilitätsadapter relevant sind:</span><span class="sxs-lookup"><span data-stu-id="4a3da-141">The  `AdapterConfig` contains the Persistent Chat compliance configuration that is relevant to the compliance adapter:</span></span>

```
void SetConfig(AdapterConfig config)
```

<span data-ttu-id="4a3da-142">Der Kompatibilität für Persistent Chat Server Ruft die folgende Methode in regelmäßigen Abständen als neue Daten übersetzt.</span><span class="sxs-lookup"><span data-stu-id="4a3da-142">The Persistent Chat Compliance server calls the following method at periodic intervals as long as there is new data to translate.</span></span> <span data-ttu-id="4a3da-143">Dieses Zeitintervall ist gleich der `RunInterval` wie in den beständigen Chat Kompatibilitätskonfiguration eingerichtet sind:</span><span class="sxs-lookup"><span data-stu-id="4a3da-143">This time interval is equal to the  `RunInterval` as set in the Persistent Chat Compliance configuration:</span></span>

```
void Translate(ConversationCollection conversations)
```

<span data-ttu-id="4a3da-144">Die `ConversationCollection` enthält die unterhaltungsinformationen, die von dem Zeitpunkt der letzten erfasst wurde diese Methode wurde aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="4a3da-144">The  `ConversationCollection` contains the conversation information that was collected from the last time this method was called.</span></span>

## <a name="customize-the-xslt-definition-file"></a><span data-ttu-id="4a3da-145">Anpassen der XSLT-Definitionsdatei</span><span class="sxs-lookup"><span data-stu-id="4a3da-145">Customize the XSLT definition file</span></span>

<span data-ttu-id="4a3da-p111">Die Konformitätsdaten werden als XML ausgegeben; Sie können sie mithilfe einer XSLT-Definitionsdatei in das von Ihrer Organisation bevorzugte Format umwandeln. In diesem Thema wird die vom Konformitätsdienst erstellte XML-Datei beschrieben. Zudem werden Beispiele für XSLT-Definitions- und Ausgabedateien bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="4a3da-p111">The compliance data is delivered as XML, which you can transform into the format that best fits your organization, by using an XSLT definition file. This topic describes the XML file that the Compliance service creates. It also provides samples of XSLT definition and output files.</span></span>

### <a name="output-format"></a><span data-ttu-id="4a3da-149">Ausgabeformat</span><span class="sxs-lookup"><span data-stu-id="4a3da-149">Output format</span></span>

<span data-ttu-id="4a3da-150">Wie im folgenden Codebeispiel dargestellt ist die Ausgabe des Konformitätsdiensts nach Unterhaltungen (dem Unterhaltungselement) und Nachrichten (dem Nachrichtenelement) kategorisiert:</span><span class="sxs-lookup"><span data-stu-id="4a3da-150">The Compliance service output is categorized by conversation (the Conversation element) and then by message (the Messages element), as shown in the following code sample:</span></span>

```
<?xml version="1.0" encoding="utf-8" ?> 
<Conversations xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Conversation>
    <Channel uri="ma-chan://litwareinc.com/300" name="ma-chan://litwareinc.com/300" islogged="" /> 
    <!--FirstMessage goes here --!>
    <Messages> 
      <!—Messages go here--!>
    </Messages>
    <StartTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
    <EndTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
  </Conversation>
</Conversations>
```

<span data-ttu-id="4a3da-p112">Ein Unterhaltungselement enthält vier Elemente („Channel“, „FirstMessage“, „StartTimeUTC“ und „EndTimeUTC“). Das Element „Channel“ enthält den Uniform Resource Identifier (URI) des Chatrooms und das Element „FirstMessage“ beschreibt das erste Element im Nachrichtenelement. Die Elemente „StartTimeUTC“ und „EndTimeUTC“ enthalten wie im folgenden Codebeispiel dargestellt Informationen zu den Start- und Endzeiten der Unterhaltung.</span><span class="sxs-lookup"><span data-stu-id="4a3da-p112">A Conversation element contains four elements (Channel, FirstMessage, StartTimeUTC, and EndTimeUTC). The Channel element contains the Uniform Resource Identifier (URI) of the chat room, and the FirstMessage element describes the first message in the Messages element. The StartTimeUTC and EndTimeUTC elements provide the start and end times for the conversation, as shown in the following code sample:</span></span>

```
<<FirstMessage type="JOIN" content="" id="0">
      <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
      <DateTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
</FirstMessage>
```

<span data-ttu-id="4a3da-p113">Ein Nachrichtenelement enthält zwei Elemente („Sender“ und „DateTimeUTC“) und drei Attribute („Type“, „Content“ und „ID“). Das Element „Sender“ steht für den Benutzer, der die Nachricht sendet, und das Element „DateTimeUTC“ gibt an, wann ein Ereignis auftritt, wie im folgenden Codebeispiel dargestellt:</span><span class="sxs-lookup"><span data-stu-id="4a3da-p113">A Message element contains two elements (Sender and DateTimeUTC) and three attributes (Type, Content, and ID). The Sender element represents the user who sends the message, and the DateTimeUTC element represents when an event occurs, as shown in the following code sample:</span></span>

```
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message>
```

<span data-ttu-id="4a3da-156">In der folgenden Tabelle werden die Nachrichtenattribute „Type“, „Content“ und „ID“ beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4a3da-156">The following table describes the message attributes Type, Content, and ID.</span></span>

<span data-ttu-id="4a3da-157">**Nachrichtenelementattribute**</span><span class="sxs-lookup"><span data-stu-id="4a3da-157">**Messages Element Attributes**</span></span>

|<span data-ttu-id="4a3da-158">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="4a3da-158">**Attribute**</span></span>|<span data-ttu-id="4a3da-159">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="4a3da-159">**Description**</span></span>|<span data-ttu-id="4a3da-160">**Optional/erforderlich**</span><span class="sxs-lookup"><span data-stu-id="4a3da-160">**Optional/Required**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4a3da-161">Typ</span><span class="sxs-lookup"><span data-stu-id="4a3da-161">Type</span></span>  <br/> |<span data-ttu-id="4a3da-p114">Gibt den Nachrichtentyp an. Die Nachrichtentypen werden in der Tabelle „Nachrichtenelemente – Nachrichtentypen“ beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4a3da-p114">Specifies the message type. The message types are described in the Message Elements Message Types table.</span></span>  <br/> |<span data-ttu-id="4a3da-164">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="4a3da-164">Required</span></span>  <br/> |
|<span data-ttu-id="4a3da-165">Content</span><span class="sxs-lookup"><span data-stu-id="4a3da-165">Content</span></span>  <br/> |<span data-ttu-id="4a3da-p115">Enthält den Inhalt der Nachricht. Nachrichten vom Typ „Join“ oder „Part“ verwenden dieses Attribut nicht.</span><span class="sxs-lookup"><span data-stu-id="4a3da-p115">Contains the content of the message. Messages with a Type of Join or Part do not use this attribute.</span></span>  <br/> |<span data-ttu-id="4a3da-168">Optional</span><span class="sxs-lookup"><span data-stu-id="4a3da-168">Optional</span></span>  <br/> |
|<span data-ttu-id="4a3da-169">ID</span><span class="sxs-lookup"><span data-stu-id="4a3da-169">ID</span></span>  <br/> |<span data-ttu-id="4a3da-p116">Gibt die eindeutige ID des Inhalts an. Dieses Attribut wird nur mit Nachrichten vom Typ „Chat“ verwendet.</span><span class="sxs-lookup"><span data-stu-id="4a3da-p116">Specifies the unique ID of the content. This attribute is used only with messages with a Type of Chat.</span></span>  <br/> |<span data-ttu-id="4a3da-172">Optional</span><span class="sxs-lookup"><span data-stu-id="4a3da-172">Optional</span></span>  <br/> |

<span data-ttu-id="4a3da-p117">Jedes „Sender“-Element enthält fünf Attribute: „user name“, „ID“, „email“, „internal“ und „URI“. Diese Attribute sind in der folgenden Tabelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4a3da-p117">Each Sender element contains five attributes: the user name, ID, email, internal, and URI. These attributes are described in the following table.</span></span>

<span data-ttu-id="4a3da-175">**„Sender“-Elementattribute**</span><span class="sxs-lookup"><span data-stu-id="4a3da-175">**Sender Element Attributes**</span></span>

|<span data-ttu-id="4a3da-176">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="4a3da-176">**Attribute**</span></span>|<span data-ttu-id="4a3da-177">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="4a3da-177">**Description**</span></span>|<span data-ttu-id="4a3da-178">**Optional/erforderlich**</span><span class="sxs-lookup"><span data-stu-id="4a3da-178">**Optional/Required**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4a3da-179">Username</span><span class="sxs-lookup"><span data-stu-id="4a3da-179">Username</span></span>  <br/> |<span data-ttu-id="4a3da-180">Der Name des Absenders.</span><span class="sxs-lookup"><span data-stu-id="4a3da-180">The name of the sender.</span></span>  <br/> |<span data-ttu-id="4a3da-181">Optional</span><span class="sxs-lookup"><span data-stu-id="4a3da-181">Optional</span></span>  <br/> |
|<span data-ttu-id="4a3da-182">ID</span><span class="sxs-lookup"><span data-stu-id="4a3da-182">ID</span></span>  <br/> |<span data-ttu-id="4a3da-183">Eindeutige ID des Absenders</span><span class="sxs-lookup"><span data-stu-id="4a3da-183">The sender's unique ID.</span></span>  <br/> |<span data-ttu-id="4a3da-184">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="4a3da-184">Required</span></span>  <br/> |
|<span data-ttu-id="4a3da-185">E-Mail</span><span class="sxs-lookup"><span data-stu-id="4a3da-185">Email</span></span>  <br/> |<span data-ttu-id="4a3da-186">E-Mail-Adresse des Absenders.</span><span class="sxs-lookup"><span data-stu-id="4a3da-186">The sender's email address.</span></span>  <br/> |<span data-ttu-id="4a3da-187">Optional</span><span class="sxs-lookup"><span data-stu-id="4a3da-187">Optional</span></span>  <br/> |
|<span data-ttu-id="4a3da-188">Intern</span><span class="sxs-lookup"><span data-stu-id="4a3da-188">Internal</span></span>  <br/> |<span data-ttu-id="4a3da-p118">Gibt an, ob es sich um einen internen Benutzer oder einen Verbundbenutzer handelt. Bei Festlegung des Werts auf „true“ (wahr) ist der Benutzer intern.</span><span class="sxs-lookup"><span data-stu-id="4a3da-p118">Determines whether the user is an internal user or a federated user. If the value is set to true, the user is internal.</span></span>  <br/> |<span data-ttu-id="4a3da-191">Optional</span><span class="sxs-lookup"><span data-stu-id="4a3da-191">Optional</span></span>  <br/> |
|<span data-ttu-id="4a3da-192">Uri</span><span class="sxs-lookup"><span data-stu-id="4a3da-192">Uri</span></span>  <br/> |<span data-ttu-id="4a3da-193">Die SIP-URI des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="4a3da-193">The user's SIP URI.</span></span>  <br/> |<span data-ttu-id="4a3da-194">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="4a3da-194">Required</span></span>  <br/> |

<span data-ttu-id="4a3da-195">Die folgenden Beispiele zeigen den Nachrichtentypen, dass das Element Nachrichten enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="4a3da-195">The following examples show the message types that the Messages element can contain.</span></span> <span data-ttu-id="4a3da-196">Sie enthält auch Beispiele für die Verwendung der einzelnen Elemente.</span><span class="sxs-lookup"><span data-stu-id="4a3da-196">It also provides examples of how each element is used.</span></span>

<span data-ttu-id="4a3da-197">Join - ein Benutzer einen Chatroom betritt.</span><span class="sxs-lookup"><span data-stu-id="4a3da-197">Join - A user joins a chat room.</span></span>

```
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message
```

<span data-ttu-id="4a3da-198">Teil – ein Benutzer einen Chatroom verlässt.</span><span class="sxs-lookup"><span data-stu-id="4a3da-198">Part - A user leaves a chat room.</span></span>

```
<Message type="PART" content="" id="0">
  < Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
</Message>
```

<span data-ttu-id="4a3da-199">Chat - e-Mail-Adresse des Absenders.</span><span class="sxs-lookup"><span data-stu-id="4a3da-199">Chat - The sender's email address.</span></span>

```
<Message type="CHAT" content="hello" id="1">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351800522" string="2008-03-12T19:56:40.522264Z" long="633409486005222640" /> 
</Message>
```

<span data-ttu-id="4a3da-200">Backchat - fordert ein Benutzer Inhalte aus den Chatverlauf.</span><span class="sxs-lookup"><span data-stu-id="4a3da-200">Backchat - A user requests content from chat history.</span></span>

```
<Message type="BACKCHAT" content="backchatcontent" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206034385284" string="2008-03-20T17:33:05.2841594Z" long="633416311852841594" /> 
</Message>
```

<span data-ttu-id="4a3da-201">Dateien hochladen - ein Benutzer eine Datei hochlädt.</span><span class="sxs-lookup"><span data-stu-id="4a3da-201">File upload - A user uploads a file.</span></span>

```
<Message type="FILEUPLOAD" content="0988239a-bb66-4616-90a4-b07771a2097c.txt" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351828975" string="2008-03-12T19:57:08.9755711Z" long="633409486289755711" /> 
</Message>
```

<span data-ttu-id="4a3da-202">Dateidownload – ein Benutzer eine Datei herunterlädt.</span><span class="sxs-lookup"><span data-stu-id="4a3da-202">File download - A user downloads a file.</span></span>

```
<Message type="FILEDOWNLOAD" content="006074ca-24f0-4b35-8bd8-98006a2d1aa8.txt" id="0">
  <Sender UserName="kazuto@litwareinc.com" id="10" email="" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212611141851" string="2008-06-04T20:25:41.8518646Z" long="633482079418518646" /> 
</Message>
```

### <a name="default-persistent-chat-output-xsd-and-example-xsl-transform"></a><span data-ttu-id="4a3da-203">Standardwert beständigen Chat XSD-Ausgabe und Beispiel-XSL-Transformation</span><span class="sxs-lookup"><span data-stu-id="4a3da-203">Default Persistent Chat Output XSD and Example XSL Transform</span></span>

<span data-ttu-id="4a3da-204">Das folgende Codebeispiel enthält die standardmäßige Ausgabe des Konformitätsservers.</span><span class="sxs-lookup"><span data-stu-id="4a3da-204">The following code sample contains the default output from the Compliance Server:</span></span>

```
<?xml version="1.0" encoding="utf-8"?>
<xs:schema id="Conversations" xmlns="" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">
   <xs:simpleType name="ComplianceMessageType">
      <xs:restriction base="xs:string">
        <xs:enumeration value="JOIN"/>
        <xs:enumeration value="PART"/>
        <xs:enumeration value="CHAT"/>
        <xs:enumeration value="BACKCHAT"/>
        <xs:enumeration value="FILEUPLOAD"/>
        <xs:enumeration value="FILEDOWNLOAD"/>
      </xs:restriction>
    </xs:simpleType>

  <xs:element name="Sender">
    <xs:complexType>
      <xs:attribute name="UserName" type="xs:string" />
      <xs:attribute name="id" type="xs:int" />
      <xs:attribute name="email" type="xs:string" use="optional" />
      <xs:attribute name="internal" type="xs:boolean" use="optional" >
        <xs:annotation><xs:documentation>If the user is internal or federated</xs:documentation></xs:annotation>
      </xs:attribute>
      <xs:attribute name="uri" type="xs:anyURI" use="optional" />
    </xs:complexType>
  </xs:element>
  <xs:element name="DateTimeUTC">
    <xs:complexType>
      <xs:attribute name="since1970" type="xs:long" />
      <xs:attribute name="string" type="xs:string" />
      <xs:attribute name="long" type="xs:long" />
    </xs:complexType>
  </xs:element>
  <xs:element name="Conversations" msdata:IsDataSet="true" msdata:UseCurrentLocale="true">
    <xs:complexType>
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element ref="Sender" />
        <xs:element ref="DateTimeUTC" />
        <xs:element name="Conversation">
          <xs:complexType>
            <xs:sequence>
              <xs:element name="Channel" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:attribute name="uri" type="xs:anyURI" />
                  <xs:attribute name="name" type="xs:string" use="optional" />
                </xs:complexType>
              </xs:element>
              <xs:element name="FirstMessage" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:sequence>
                    <xs:element ref="Sender" minOccurs="0" maxOccurs="unbounded" />
                    <xs:element ref="DateTimeUTC" minOccurs="0" maxOccurs="unbounded" />
                  </xs:sequence>
                  <xs:attribute name="type" type="ComplianceMessageType" />
                  <xs:attribute name="content" type="xs:string" />
                  <xs:attribute name="id" type="xs:int" />
                </xs:complexType>
              </xs:element>
              <xs:element name="Messages" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:sequence>
                    <xs:element name="Message" minOccurs="0" maxOccurs="unbounded">
                      <xs:complexType>
                        <xs:sequence>
                          <xs:element ref="Sender" minOccurs="0" maxOccurs="unbounded" />
                          <xs:element ref="DateTimeUTC" minOccurs="0" maxOccurs="unbounded" />
                        </xs:sequence>
                        <xs:attribute name="type" type="ComplianceMessageType" />
                        <xs:attribute name="content" type="xs:string" />
                        <xs:attribute name="id" type="xs:int" />
                      </xs:complexType>
                    </xs:element>
                  </xs:sequence>
                </xs:complexType>
              </xs:element>
              <xs:element name="StartTimeUTC" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:attribute name="since1970" type="xs:long" />
                  <xs:attribute name="string" type="xs:string" />
                  <xs:attribute name="long" type="xs:long" />
                </xs:complexType>
              </xs:element>
              <xs:element name="EndTimeUTC" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:attribute name="since1970" type="xs:long" />
                  <xs:attribute name="string" type="xs:string" />
                  <xs:attribute name="long" type="xs:long" />
                </xs:complexType>
              </xs:element>
            </xs:sequence>
          </xs:complexType>
        </xs:element>
      </xs:choice>
    </xs:complexType>
  </xs:element>
</xs:schema>
```

<span data-ttu-id="4a3da-205">Das folgende Codebeispiel enthält ein Beispiel einer XSL-Transformation.</span><span class="sxs-lookup"><span data-stu-id="4a3da-205">The following code sample contains a sample XSL transform:</span></span>

```
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xs="http://www.w3.org/2001/XMLSchema" exclude-result-prefixes="xs">
   <xsl:output method="xml" encoding="UTF-8" indent="yes" />

   <xsl:template match="/">
      <FileDump>
         <xsl:apply-templates />
      </FileDump>
   </xsl:template>

   <xsl:template match="Conversation">
      <xsl:variable name="chanName" select="Channel/@name" />
      <Conversation Perspective="{$chanName}_group_channel">
         <RoomID><xsl:value-of select="Channel/@name" /></RoomID>
         <StartTimeUTC><xsl:value-of select="StartTimeUTC/@since1970" /></StartTimeUTC>
         <xsl:apply-templates />
         <EndTimeUTC><xsl:value-of select="EndTimeUTC/@since1970" /></EndTimeUTC>
      </Conversation>
   </xsl:template>

   <xsl:template match="Message">
      <xsl:choose>
         <xsl:when test="@type='JOIN'">
            <ParticipantEntered>
               <xsl:call-template name="DateTimeAndLogin" />
               <InternalFlag><xsl:value-of select="Sender/@internal" /></InternalFlag>
               <ConversationID><xsl:value-of select="../../Channel/@name" /></ConversationID>
               <CorporateEmailID><xsl:value-of select="Sender/@email" /></CorporateEmailID>
            </ParticipantEntered>
         </xsl:when>

         <xsl:when test="@type='PART'">
            <ParticipantLeft>
               <xsl:call-template name="DateTimeAndLogin" />
               <InternalFlag><xsl:value-of select="Sender/@internal" /></InternalFlag>
               <ConversationID><xsl:value-of select="../../Channel/@name" /></ConversationID>
               <CorporateEmailID><xsl:value-of select="Sender/@email" /></CorporateEmailID>
            </ParticipantLeft>
         </xsl:when>

         <xsl:when test="@type='FILEUPLOAD' or @type='FILEDOWNLOAD'">
            <FileTransferStarted>
               <xsl:call-template name="DateTimeAndLogin" />
               <FileName><xsl:value-of select="@content" /></FileName>
            </FileTransferStarted>
            <FileTransferEnded>
               <xsl:call-template name="DateTimeAndLogin" />
               <FileName><xsl:value-of select="@content" /></FileName>
               <Status>Completed</Status>
            </FileTransferEnded>
         </xsl:when>

         <xsl:when test="@type='CHAT' or @type='BACKCHAT'">
            <Message>
               <xsl:call-template name="DateTimeAndLogin" />
               <Content><xsl:value-of select="@content" /></Content>
            </Message>
         </xsl:when>

         <xsl:otherwise />
      </xsl:choose>
   </xsl:template>

   <xsl:template name="DateTimeAndLogin">
      <LoginName><xsl:value-of select="Sender/@userName" /></LoginName>
      <DateTimeUTC><xsl:value-of select="DateTimeUTC/@since1970" /></DateTimeUTC>
   </xsl:template>
</xsl:stylesheet>
```