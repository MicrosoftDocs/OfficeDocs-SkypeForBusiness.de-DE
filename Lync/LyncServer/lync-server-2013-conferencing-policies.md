---
title: 'Lync Server 2013: Konferenzrichtlinien'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conferencing policies
ms:assetid: 8f92eb7c-ee66-4df6-a726-4bff93b122cb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688133(v=OCS.15)
ms:contentKeyID: 49733732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b60b521c69b821dacfe8bd569a6300b4c21e0287
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839468"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-policies-in-lync-server-2013"></a><span data-ttu-id="a2fce-102">Konferenzrichtlinien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2fce-102">Conferencing policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2fce-103">_**Letztes Änderungsdatum des Themas:** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="a2fce-103">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="a2fce-104">Konferenzrichtlinie definiert die Features und Funktionen, die Benutzer während einer Konferenz (auch als Besprechung bezeichnet) zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="a2fce-104">Conferencing policy defines the features and capabilities that users have available during a conference (also known as a meeting).</span></span> <span data-ttu-id="a2fce-105">Konferenzrichtlinieneinstellungen umfassen eine breite Auswahl an Planungs- und Teilnahmeoptionen, von der Verwendung von IP-Audio und -Video in einer Besprechung bis hin zur Höchstzahl der möglichen Teilnehmer.</span><span class="sxs-lookup"><span data-stu-id="a2fce-105">Conferencing policy settings encompass a wide variety of scheduling and participation options, ranging from whether a meeting can include IP audio and video to the maximum number of people who can attend.</span></span> <span data-ttu-id="a2fce-106">Administratoren können Konferenzrichtlinien verwenden, um Sicherheit, Bandbreite und rechtliche Aspekte von Besprechungen zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="a2fce-106">Administrators can use conferencing policy to manage security, bandwidth, and legal aspects of meetings.</span></span>

<span data-ttu-id="a2fce-107">Die Konferenzrichtlinie kann auf drei Ebenen definiert werden: auf globaler, auf Standort- und auf Benutzerebene.</span><span class="sxs-lookup"><span data-stu-id="a2fce-107">You can define conferencing policy on three levels: global scope, site scope, and user scope.</span></span> <span data-ttu-id="a2fce-108">Die Einstellungen gelten für einen bestimmten Benutzer vom engsten bis hin zum weitesten Bereich.</span><span class="sxs-lookup"><span data-stu-id="a2fce-108">Settings apply to a specific user from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="a2fce-109">Wenn Sie einem Benutzer eine Benutzerrichtlinie zuweisen, haben diese Einstellungen Vorrang.</span><span class="sxs-lookup"><span data-stu-id="a2fce-109">If you assign a user policy to a user, those settings take precedence.</span></span> <span data-ttu-id="a2fce-110">Wenn Sie keine Benutzerrichtlinie zuweisen, gelten die Standorteinstellungen.</span><span class="sxs-lookup"><span data-stu-id="a2fce-110">If you do not assign a user policy, site settings apply.</span></span> <span data-ttu-id="a2fce-111">Gelten weder Benutzer- noch Standortrichtlinien, stellt die globale Richtlinie die Standardeinstellungen bereit.</span><span class="sxs-lookup"><span data-stu-id="a2fce-111">If no user or site policies apply, global policy provides the default settings.</span></span>

<span data-ttu-id="a2fce-112">Eine globale Richtlinie ist standardmäßig vorhanden, sodass Sie keine neue globale Richtlinie erstellen können.</span><span class="sxs-lookup"><span data-stu-id="a2fce-112">A global policy exists by default, so you cannot create a new global policy.</span></span> <span data-ttu-id="a2fce-113">Sie können auch die vorhandene globale Richtlinie nicht löschen, aber Sie können die vorhandene globale Richtlinie so ändern, dass die Standardeinstellungen angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="a2fce-113">You also cannot delete the existing global policy, but you can change the existing global policy to customize your default settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a2fce-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a2fce-114">In This Section</span></span>

  - [<span data-ttu-id="a2fce-115">Anzeigen von Konferenzrichtlinien Informationen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2fce-115">View conferencing policy information in Lync Server 2013</span></span>](lync-server-2013-view-conferencing-policy-information.md)

  - [<span data-ttu-id="a2fce-116">Erstellen oder Ändern einer konferenzrichtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2fce-116">Create or modify a conferencing policy in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-conferencing-policy.md)

  - [<span data-ttu-id="a2fce-117">Löschen einer vorhandenen konferenzrichtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2fce-117">Delete an existing conferencing policy in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-conferencing-policy.md)

  - [<span data-ttu-id="a2fce-118">Referenz für konferenzrichtlinieneinstellungen für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2fce-118">Conferencing policy settings reference for Lync Server 2013</span></span>](lync-server-2013-conferencing-policy-settings-reference.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

