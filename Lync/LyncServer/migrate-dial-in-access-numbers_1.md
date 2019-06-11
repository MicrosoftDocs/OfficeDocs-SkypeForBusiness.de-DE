---
title: Migrieren von Zugriffsnummern für die Einwahl
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate dial-in access numbers
ms:assetid: 568a94b7-a697-4ab2-9008-dc9ecc1c87c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204898(v=OCS.15)
ms:contentKeyID: 48184171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b86db6e669fd5f52827591c25e5bb237bd9ee012
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847121"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="92163-102">Migrieren von Zugriffsnummern für die Einwahl</span><span class="sxs-lookup"><span data-stu-id="92163-102">Migrate dial-in access numbers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92163-103">_**Letztes Änderungsdatum des Themas:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="92163-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="92163-104">Zum Migrieren von Einwahl Zugriffsnummern sind zwei Schritte erforderlich: Ausführen des Cmdlets " **Import-CsLegacyConfiguration** " (bereits in [Importieren von Richtlinien und Einstellungen](import-policies-and-settings.md)) zum Migrieren von Wählplänen und anderen Einstellungen für Einwahlnummern und Ausführen des \*\* Move-CsApplicationEndpoint-\*\* Cmdlet, um die Kontaktobjekte zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="92163-104">Migrating dial-in access numbers requires two steps: running the **Import-CsLegacyConfiguration** cmdlet (completed earlier in [Import policies and settings](import-policies-and-settings.md)) to migrate dial plans and other dial-in access number settings, and running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span>

<div>

## <a name="to-migrate-dial-in-access-numbers"></a><span data-ttu-id="92163-105">So migrieren Sie Einwahl Zugriffsnummern</span><span class="sxs-lookup"><span data-stu-id="92163-105">To migrate dial-in access numbers</span></span>

1.  <span data-ttu-id="92163-106">Öffnen Sie das Office Communications Server 2007 R2-Verwaltungstool.</span><span class="sxs-lookup"><span data-stu-id="92163-106">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="92163-107">Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf den Knoten Gesamtstruktur, klicken Sie auf **Eigenschaften**, und klicken Sie dann auf **Eigenschaften der Konferenzzentrale**.</span><span class="sxs-lookup"><span data-stu-id="92163-107">In the console tree, right-click the forest node, click **Properties**, and then click **Conferencing Attendant Properties**.</span></span>

3.  <span data-ttu-id="92163-108">Klicken Sie auf der Registerkarte **Access-Telefonnummern** auf **gewartet nach Pool** , um die Access-Telefonnummern nach dem zugehörigen Pool zu sortieren, und identifizieren Sie alle Zugriffsnummern für den Pool, aus dem Sie migrieren möchten.</span><span class="sxs-lookup"><span data-stu-id="92163-108">On the **Access Phone Numbers** tab, click **Serviced by Pool** to sort the access phone numbers by their associated pool, and identify all the access numbers for the pool from which you are migrating.</span></span>

4.  <span data-ttu-id="92163-109">Um den SIP-URI für jede Zugriffsnummer zu identifizieren, doppelklicken Sie auf die Zugriffsnummer, um das Dialogfeld **Konferenzzentrale Nummer bearbeiten** zu öffnen, und schauen Sie unter **SIP-URI**nach.</span><span class="sxs-lookup"><span data-stu-id="92163-109">To identify the SIP URI for each access number, double-click the access number to open the **Edit Conferencing Attendant Number** dialog box, and look under **SIP URI**.</span></span>

5.  <span data-ttu-id="92163-110">Öffnen Sie die lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="92163-110">Open the Lync Server Management Shell.</span></span>

6.  <span data-ttu-id="92163-111">Führen Sie die folgenden Schritte aus, um jede Einwahl Zugriffsnummer in einen Pool zu verschieben, der auf lync Server 2013 gehostet wird:</span><span class="sxs-lookup"><span data-stu-id="92163-111">To move each dial-in access number to a pool hosted on Lync Server 2013, run:</span></span>
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

7.  <span data-ttu-id="92163-112">Überprüfen Sie im Office Communications Server 2007 R2-Verwaltungstool auf der Registerkarte **Access-Telefonnummern** , ob keine Einwahl Zugriffsnummern für den Office Communications Server 2007 R2-Pool vorhanden sind, von dem aus Sie migrieren.</span><span class="sxs-lookup"><span data-stu-id="92163-112">In the Office Communications Server 2007 R2 Administrative tool, on the **Access Phone Numbers** tab, verify that no dial-in access numbers remain for the Office Communications Server 2007 R2 pool from which you are migrating.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

