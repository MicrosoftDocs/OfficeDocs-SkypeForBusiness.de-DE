---
title: 'Lync Server 2013: Gruppenrichtlinieneinstellungen für lync 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group Policy settings for Lync 2013
ms:assetid: 5917a52b-dae0-4ec0-8548-a68dc20ab71c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204924(v=OCS.15)
ms:contentKeyID: 48184235
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba88fdce88280597e9e621c13267de2b9b76d0fb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030358"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-policy-settings-for-lync-2013"></a><span data-ttu-id="ae0f8-102">Gruppenrichtlinieneinstellungen für lync 2013</span><span class="sxs-lookup"><span data-stu-id="ae0f8-102">Group Policy settings for Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae0f8-103">_**Letztes Änderungsstand des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="ae0f8-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="ae0f8-104">In früheren Versionen von lync und Office Communicator Stand eine eigenständige administrative Vorlage "Communicator. adm" zum Konfigurieren von Clientgruppen Richtlinieneinstellungen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="ae0f8-104">In previous versions of Lync and Office Communicator, a stand-alone Communicator.adm administrative template was available for configuring client Group Policy settings.</span></span> <span data-ttu-id="ae0f8-105">Für lync 2013 werden neue administrative Vorlagendateien (ADMX-und ADML-Dateien) zusammen mit der administrativen Vorlage für Office-Gruppenrichtlinien eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="ae0f8-105">For Lync 2013, new administrative template files (.admx and .adml files) are included along with the Office Group Policy Administrative Template.</span></span> <span data-ttu-id="ae0f8-106">Die Verfügbarkeit von lync 2013. ADMX-und. ADML-Dateien ermöglicht Ihnen das Herunterladen von Vorlagen und das zentrale Verwalten von Gruppenrichtlinieneinstellungen für alle Ihre Office-Programme und Sprachpakete.</span><span class="sxs-lookup"><span data-stu-id="ae0f8-106">The availability of Lync 2013 .admx and .adml files allows you to download templates and centrally manage Group Policy settings for all your Office programs and language packs.</span></span> <span data-ttu-id="ae0f8-107">Ausführliche Informationen finden Sie unter "Office 2013 administrative Template Files (ADMX, ADML)" in der Office 2013- <http://go.microsoft.com/fwlink/p/?linkid=267516>Dokumentation unter.</span><span class="sxs-lookup"><span data-stu-id="ae0f8-107">For details, see “Office 2013 Administrative Template files (ADMX, ADML)” in the Office 2013 documentation at <http://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

<div>

## <a name="client-bootstrapping-policies"></a><span data-ttu-id="ae0f8-108">Richtlinien für das Clientbootstrapping</span><span class="sxs-lookup"><span data-stu-id="ae0f8-108">Client Bootstrapping Policies</span></span>

<span data-ttu-id="ae0f8-109">Es gibt verschiedene Richtlinien für das Clientbootstrapping, die Sie konfigurieren sollten, bevor sich Benutzer zum ersten Mal beim Server anmelden.</span><span class="sxs-lookup"><span data-stu-id="ae0f8-109">There are several client bootstrapping policies that you should configure before users sign in to the server for the first time.</span></span> <span data-ttu-id="ae0f8-110">Da diese Richtlinien in Kraft treten, bevor sich der Client anmeldet und In-Band-Bereitstellungseinstellungen vom Server empfängt, können Sie diese Richtlinien mithilfe von Gruppenrichtlinien konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ae0f8-110">Because these policies take effect before the client signs in and begins receiving in-band provisioning settings from the server, you can use Group Policy to configure them.</span></span> <span data-ttu-id="ae0f8-111">Weitere Informationen finden Sie unter [Configuring clientbootstrapping Policies in lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="ae0f8-111">For more information, see [Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

