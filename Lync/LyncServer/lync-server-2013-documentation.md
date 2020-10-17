---
title: 'Lync Server 2013: Dokumentation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Documentation
ms:assetid: 5a69c0a2-0986-49c3-809c-89bc175a34ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720335(v=OCS.15)
ms:contentKeyID: 63969609
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2785391f93f2844809aaad06e4efff9c2e86505d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501172"
---
# <a name="documentation-in-lync-server-2013"></a><span data-ttu-id="1ac9c-102">Dokumentation in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ac9c-102">Documentation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ac9c-103">_**Letztes Änderungsstand des Themas:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="1ac9c-103">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="1ac9c-104">Das MOF-Modell besteht aus vielen Dienstverwaltungsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="1ac9c-104">The MOF model is composed of many service management functions.</span></span> <span data-ttu-id="1ac9c-105">Dokumentation darüber, wie und wann Aufgaben ausgeführt werden, können für Mitglieder desselben Teams oder mit anderen Teams freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1ac9c-105">Documentation about how and when tasks are performed can be shared with members of the same team or with other teams.</span></span> <span data-ttu-id="1ac9c-106">Die Methode zum Speichern und Freigeben von Dokumentation kann je nach Typ der Funktion variieren.</span><span class="sxs-lookup"><span data-stu-id="1ac9c-106">The method of storing and sharing documentation can vary according to the type of function.</span></span> <span data-ttu-id="1ac9c-107">Beispielsweise können die Verfahren für die Systemverwaltung als Word-Dokumente gespeichert werden, da Sie häufig gedruckt und referenziert werden.</span><span class="sxs-lookup"><span data-stu-id="1ac9c-107">For example, the procedures for system administration may be stored as Word documents because they are likely to be printed and referenced frequently.</span></span> <span data-ttu-id="1ac9c-108">Konfigurationsverwaltungsinformationen werden möglicherweise automatisch generiert und in einer Datenbank gespeichert, um eine einfache Suche und Indizierung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1ac9c-108">Configuration management information may be automatically generated and stored in a database for easy searching and indexing.</span></span> <span data-ttu-id="1ac9c-109">Einige Dokumentationen sind möglicherweise vertraulich und sollten eingeschränkt sein.</span><span class="sxs-lookup"><span data-stu-id="1ac9c-109">Some documentation may be sensitive and should be restricted.</span></span>

<div>

## <a name="document-management-systems"></a><span data-ttu-id="1ac9c-110">Dokumentverwaltungssysteme</span><span class="sxs-lookup"><span data-stu-id="1ac9c-110">Document management systems</span></span>

<span data-ttu-id="1ac9c-111">Ein Dokumentations Verwaltungssystem fungiert als zentrales Repository für Dokumente und stellt sicher, dass nur die neueste Version eines Dokuments zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="1ac9c-111">A documentation management system acts as a central repository for documents and helps ensure that only the latest revision of a document is available.</span></span> <span data-ttu-id="1ac9c-112">Sie können die ältere Version des Dokuments auch als Referenz archivieren.</span><span class="sxs-lookup"><span data-stu-id="1ac9c-112">You can also consider archiving the older version of the document for reference.</span></span> <span data-ttu-id="1ac9c-113">Lync Server bietet für diese Aufgabe geeignete Funktionen.</span><span class="sxs-lookup"><span data-stu-id="1ac9c-113">Lync Server provides functionality suitable to this task.</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="1ac9c-114">Datenbanken</span><span class="sxs-lookup"><span data-stu-id="1ac9c-114">Databases</span></span>

<span data-ttu-id="1ac9c-115">Es wurden verschiedene Tools und Verwaltungsfunktionen erörtert, die für die Verwendung von Datenbanken geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="1ac9c-115">Several tools and management functions were discussed that are suited to using databases.</span></span> <span data-ttu-id="1ac9c-116">Der Konfigurationsverwaltungsprozess verwendet wahrscheinlich automatisierte Prozesse, die große Datenmengen speichern, die indizieren und suchen erfordern.</span><span class="sxs-lookup"><span data-stu-id="1ac9c-116">The configuration management process is likely to use automated processes that store large amounts of data that require indexing and searching.</span></span> <span data-ttu-id="1ac9c-117">Support Mitarbeiter können eine Datenbank mit früheren Problemen und Lösungen durchsuchen, wenn Sie neue Probleme beheben.</span><span class="sxs-lookup"><span data-stu-id="1ac9c-117">Support staff may search a database of past issues and resolutions when troubleshooting new issues.</span></span>

<span data-ttu-id="1ac9c-118">Wahrscheinlich werden verschiedene Datenbanken für verschiedene Zwecke verwendet.</span><span class="sxs-lookup"><span data-stu-id="1ac9c-118">It is likely that there will be different databases being used for different purposes.</span></span> <span data-ttu-id="1ac9c-119">Entscheiden Sie, ob diese Datenbankenverknüpft oder kombiniert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1ac9c-119">Decide if these databases should be linked or combined.</span></span> <span data-ttu-id="1ac9c-120">Wenn der Service Desk beispielsweise mehrere Probleme mit einem allgemeinen Design identifiziert (beispielsweise neue Software, die ein Problem mit einem bestimmten Netzwerkadapter verursacht), kann der Supportmitarbeiter die Konfigurationsdatenbank Abfragen, um vorherzusagen, wie viele Computer betroffen sein könnten.</span><span class="sxs-lookup"><span data-stu-id="1ac9c-120">For example, if the service desk identifies several issues with a common theme (such as new software causing an issue with a particular network adapter), the support staff can query the configuration database to predict how many computers might be affected.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

