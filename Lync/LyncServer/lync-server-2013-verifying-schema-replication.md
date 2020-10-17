---
title: 'Lync Server 2013: Überprüfen der Schemareplikation'
description: 'Lync Server 2013: Überprüfen der Schemareplikation.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verifying schema replication
ms:assetid: ad01a7cf-aa79-4648-ba5a-a7a09172db36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412822(v=OCS.15)
ms:contentKeyID: 48185124
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 019cd06db05a9ba683767f550a712ef188b47508
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560171"
---
# <a name="verifying-active-directory-schema-replication-in-lync-server-2013"></a><span data-ttu-id="deb89-103">Überprüfen Active Directory Schemareplikation in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="deb89-103">Verifying Active Directory schema replication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="deb89-104">_**Letztes Änderungsstand des Themas:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="deb89-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="deb89-105">Überprüfen Sie vor dem Ausführen der Gesamtstrukturvorbereitung manuell, ob die Schemapartition repliziert wurde.</span><span class="sxs-lookup"><span data-stu-id="deb89-105">Before you run forest preparation, manually verify that the schema partition has been replicated.</span></span>

<div>

## <a name="to-manually-verify-schema-replication"></a><span data-ttu-id="deb89-106">So überprüfen Sie die Schemareplikation manuell</span><span class="sxs-lookup"><span data-stu-id="deb89-106">To manually verify schema replication</span></span>

1.  <span data-ttu-id="deb89-107">Melden Sie sich bei einem Domänencontroller als Mitglied der Gruppe "Organisations-Admins" an.</span><span class="sxs-lookup"><span data-stu-id="deb89-107">Log on to a domain controller as a member of the Enterprise Admins group.</span></span>

2.  <span data-ttu-id="deb89-108">Öffnen Sie den ADSI-Editor, indem Sie nacheinander auf **Start**, **Verwaltung** und dann auf **ADSI-Editor** klicken.</span><span class="sxs-lookup"><span data-stu-id="deb89-108">Open ADSI Edit by clicking **Start**, clicking **Administrative Tools**, and then clicking **ADSI Edit**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="deb89-109">Alternativ dazu können Sie <STRONG>adsiedit.msc</STRONG> auch über die Befehlszeile ausführen.</span><span class="sxs-lookup"><span data-stu-id="deb89-109">Alternatively, you can run <STRONG>adsiedit.msc</STRONG> from the command line.</span></span>

    
    </div>

3.  <span data-ttu-id="deb89-110">Klicken Sie in der MMC-Konsolenstruktur (Microsoft Management Console) auf **ADSI-Editor**, falls er nicht bereits ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="deb89-110">In the Microsoft Management Console (MMC) tree, if it is not already selected, click **ADSI Edit**.</span></span>

4.  <span data-ttu-id="deb89-111">Klicken Sie im Menü **Aktion** auf **Verbinden mit**.</span><span class="sxs-lookup"><span data-stu-id="deb89-111">On the **Action** menu, click **Connect to**.</span></span>

5.  <span data-ttu-id="deb89-112">Wählen Sie im Dialogfeld **Verbindungseinstellungen** unter **Bekannten Namenskontext auswählen** die Option **Schema** aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="deb89-112">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>

6.  <span data-ttu-id="deb89-113">Suchen Sie unter dem Schemacontainer nach "CN=ms-RTC-SIP-SchemaVersion".</span><span class="sxs-lookup"><span data-stu-id="deb89-113">Under the schema container, search for CN=ms-RTC-SIP-SchemaVersion.</span></span> <span data-ttu-id="deb89-114">Wenn dieses Objekt vorhanden und der Wert des Attributs **rangeUpper** 1150 und der Wert des Attributs **rangeLower** 3 ist, wurde das Schema erfolgreich aktualisiert und repliziert.</span><span class="sxs-lookup"><span data-stu-id="deb89-114">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, then the schema was successfully updated and replicated.</span></span> <span data-ttu-id="deb89-115">Wenn dieses Objekt nicht vorhanden ist oder die Werte der Attribute **rangeUpper** und **rangeLower** nicht diesen Werten entsprechen, wurde das Schema nicht geändert oder repliziert.</span><span class="sxs-lookup"><span data-stu-id="deb89-115">If this object does not exist or the values of the **rangeUpper** and **rangeLower** attributes are not as specified, then the schema was not modified or has not replicated.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="deb89-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="deb89-116">See Also</span></span>


[<span data-ttu-id="deb89-117">Durchführen Active Directory Schemavorbereitung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="deb89-117">Running Active Directory schema preparation in Lync Server 2013</span></span>](lync-server-2013-running-schema-preparation.md)  


[<span data-ttu-id="deb89-118">Vorbereiten des Active Directory Schemas in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="deb89-118">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

