---
title: Überprüfen der Replikation der Schemapartition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
description: 'Gehen Sie wie folgt vor, um zu überprüfen, ob die Schemaerweiterung erfolgreich in Ihrer Active Directory-Domänendienst Struktur repliziert wurde:'
ms.openlocfilehash: f2e8c181f01e841ebc6b251d8215a8d448db0b04
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823269"
---
# <a name="verify-replication-of-schema-partition"></a><span data-ttu-id="26cc7-103">Überprüfen der Replikation der Schemapartition</span><span class="sxs-lookup"><span data-stu-id="26cc7-103">Verify Replication of Schema Partition</span></span>
 
<span data-ttu-id="26cc7-104">Gehen Sie wie folgt vor, um zu überprüfen, ob die Schemaerweiterung erfolgreich in Ihrer Active Directory-Domänendienst Struktur repliziert wurde:</span><span class="sxs-lookup"><span data-stu-id="26cc7-104">To verify that the schema extension have been successfully replicated in your Active Directory Domain Services forest, do the following:</span></span>
  
1. <span data-ttu-id="26cc7-105">Melden Sie sich bei einem Domänencontroller (mit Ausnahme des Domänencontrollers, der die Schemamasterrolle innehat) in Ihrer Active Directory-Domänendienste-Gesamtstruktur an, in der die Schemaerweiterungen als Mitglied der Gruppe "Organisations-Admins" angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="26cc7-105">Log on to a domain controller (other than the domain controller that holds the schema master role) in your Active Directory Domain Services forest, where the schema extensions were applied as a member of the Enterprise Admins group.</span></span>
    
2. <span data-ttu-id="26cc7-106">Öffnen Sie die ADSI-Bearbeitung: Klicken Sie auf **Start**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **ADSI-Bearbeitung**.</span><span class="sxs-lookup"><span data-stu-id="26cc7-106">Open ADSI Edit: Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="26cc7-107">Klicken Sie alternativ auf **Start**und dann auf **Ausführen**, geben Sie **Adsiedit. msc** ein, um die ADSI-Bearbeitung zu starten.</span><span class="sxs-lookup"><span data-stu-id="26cc7-107">Alternatively, click **Start**, then click **Run**, type **adsiedit.msc** to start ADSI Edit.</span></span>
  
3. <span data-ttu-id="26cc7-108">Klicken Sie in der MMC-Struktur (Microsoft Management Console) auf ADSI-Bearbeitung, wenn Sie noch nicht ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="26cc7-108">In the Microsoft Management Console (MMC) tree, if it is not already selected, click ADSI Edit.</span></span>
    
4. <span data-ttu-id="26cc7-109">Klicken Sie im Menü **Aktion** auf **Verbinden mit**.</span><span class="sxs-lookup"><span data-stu-id="26cc7-109">On the **Action** menu, click **Connect to**.</span></span>
    
5. <span data-ttu-id="26cc7-110">Wählen Sie im Dialogfeld **Verbindungseinstellungen** unter **Bekannten Namenskontext auswählen** die Option **Schema** aus und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="26cc7-110">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>
    
6. <span data-ttu-id="26cc7-111">Suchen Sie unter dem Schemacontainer nach CN=ms-RTC-SIP-SchemaVersion.</span><span class="sxs-lookup"><span data-stu-id="26cc7-111">Under the schema container, search for CN=ms-RTC-SIP-SchemaVersion.</span></span> <span data-ttu-id="26cc7-112">Wenn dieses Objekt vorhanden ist und der Wert des **rangeUpper** -Attributs 1150 ist und der Wert des **rangeLower** -Attributs 3 ist, wurde das Schema erfolgreich aktualisiert und repliziert.</span><span class="sxs-lookup"><span data-stu-id="26cc7-112">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, then the schema was successfully updated and replicated.</span></span> <span data-ttu-id="26cc7-113">Wenn dieses Objekt nicht vorhanden ist oder die Werte der **rangeUpper** -und **rangeLower** -Attribute nicht wie angegeben sind, wurde das Schema nicht geändert oder nicht repliziert.</span><span class="sxs-lookup"><span data-stu-id="26cc7-113">If this object does not exist or if the values of the **rangeUpper** and **rangeLower** attributes are not as specified, then the schema was not modified or has not replicated.</span></span>
    
> [!NOTE]
> <span data-ttu-id="26cc7-114">Wenn die Überprüfung der Replikation des Schemas noch keine erfolgreiche Replikation anzeigt, warten Sie ungefähr 15 Minuten, und überprüfen Sie dann erneut.</span><span class="sxs-lookup"><span data-stu-id="26cc7-114">If your check of the replication of the schema does not yet show a successful replication, wait approximately 15 minutes and then check again.</span></span> <span data-ttu-id="26cc7-115">Die Active Directory-Replikation basiert auf einem lockeren Konsistenz Modell, und es kann einige Replikations Latenzen auf der Grundlage einer Reihe von Faktoren auf dem Server und der Infrastruktur auftreten.</span><span class="sxs-lookup"><span data-stu-id="26cc7-115">Active Directory replication is based on a loose consistency model and some replication latency can occur, based on a number of factors in the server and infrastructure.</span></span> 
  

