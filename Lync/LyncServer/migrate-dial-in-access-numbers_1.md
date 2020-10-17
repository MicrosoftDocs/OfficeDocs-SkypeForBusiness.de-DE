---
title: Migrieren von Zugriffsnummern für die Einwahl
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: 568a94b7-a697-4ab2-9008-dc9ecc1c87c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204898(v=OCS.15)
ms:contentKeyID: 48184171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc96ef027d63c5d2020bd52d55f378fcf7dacf51
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503522"
---
# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="1faeb-102">Migrieren von Zugriffsnummern für die Einwahl</span><span class="sxs-lookup"><span data-stu-id="1faeb-102">Migrate dial-in access numbers</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1faeb-103">_**Letztes Änderungsstand des Themas:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="1faeb-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="1faeb-104">Das Migrieren von Einwahlnummern erfordert zwei Schritte: Ausführen des Cmdlets " **Import-CsLegacyConfiguration** " (zuvor abgeschlossen in " [Import Policies and Settings](import-policies-and-settings.md)"), um Wählpläne und andere Einstellungen für die Einwahl Zugriffsnummer zu migrieren und das Cmdlet " **verschieben-CsApplicationEndpoint** " zum Migrieren der Kontaktobjekte auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1faeb-104">Migrating dial-in access numbers requires two steps: running the **Import-CsLegacyConfiguration** cmdlet (completed earlier in [Import policies and settings](import-policies-and-settings.md)) to migrate dial plans and other dial-in access number settings, and running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span>

<div>

## <a name="to-migrate-dial-in-access-numbers"></a><span data-ttu-id="1faeb-105">So migrieren Sie Zugriffsnummern für die Einwahl</span><span class="sxs-lookup"><span data-stu-id="1faeb-105">To migrate dial-in access numbers</span></span>

1.  <span data-ttu-id="1faeb-106">Öffnen Sie das Office Communications Server 2007 R2 Verwaltungstool.</span><span class="sxs-lookup"><span data-stu-id="1faeb-106">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="1faeb-107">Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf den Gesamtstrukturknoten, klicken Sie auf **Eigenschaften**, und klicken Sie dann auf **Eigenschaften der Konferenzzentrale**.</span><span class="sxs-lookup"><span data-stu-id="1faeb-107">In the console tree, right-click the forest node, click **Properties**, and then click **Conferencing Attendant Properties**.</span></span>

3.  <span data-ttu-id="1faeb-108">Klicken Sie auf der Registerkarte **Zugriffstelefonnummern** auf **Verarbeitet vom Pool**, um die Zugriffstelefonnummern nach dem zugeordneten Pool zu ordnen und alle Zugriffnummern für den zu migrierenden Pool zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="1faeb-108">On the **Access Phone Numbers** tab, click **Serviced by Pool** to sort the access phone numbers by their associated pool, and identify all the access numbers for the pool from which you are migrating.</span></span>

4.  <span data-ttu-id="1faeb-109">Zum Identifizieren der SIP-URI für jede Zugriffsnummer doppelklicken Sie auf die Zugriffsnummer, um das Dialogfeld **Nummer für die Konferenzzentrale bearbeiten** zu öffnen, und sehen Sie dann unter **SIP-URI** nach.</span><span class="sxs-lookup"><span data-stu-id="1faeb-109">To identify the SIP URI for each access number, double-click the access number to open the **Edit Conferencing Attendant Number** dialog box, and look under **SIP URI**.</span></span>

5.  <span data-ttu-id="1faeb-110">Öffnen Sie die Lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="1faeb-110">Open the Lync Server Management Shell.</span></span>

6.  <span data-ttu-id="1faeb-111">Führen Sie die folgenden Schritte aus, um jede Zugriffsnummer für die Einwahl in einen auf lync Server 2013 gehosteten Pool zu übertragen:</span><span class="sxs-lookup"><span data-stu-id="1faeb-111">To move each dial-in access number to a pool hosted on Lync Server 2013, run:</span></span>
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

7.  <span data-ttu-id="1faeb-112">Überprüfen Sie im Verwaltungstool Office Communications Server 2007 R2 auf der Registerkarte **Zugriffs** Telefonnummern, ob keine Einwahlnummern für den Office Communications Server 2007 R2 Pool verbleiben, von dem Sie migrieren.</span><span class="sxs-lookup"><span data-stu-id="1faeb-112">In the Office Communications Server 2007 R2 Administrative tool, on the **Access Phone Numbers** tab, verify that no dial-in access numbers remain for the Office Communications Server 2007 R2 pool from which you are migrating.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

