---
title: Überprüfen der Replikation der Schemapartition
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
description: 'Um zu überprüfen, ob die schemaerweiterung erfolgreich in Ihrer Active Directory-Domänendienste-Gesamtstruktur repliziert wurden, führen Sie folgende Schritte aus:'
ms.openlocfilehash: 38d5983623c837e931274deef7581dd1567fc492
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234859"
---
# <a name="verify-replication-of-schema-partition"></a><span data-ttu-id="7d500-103">Überprüfen der Replikation der Schemapartition</span><span class="sxs-lookup"><span data-stu-id="7d500-103">Verify Replication of Schema Partition</span></span>
 
<span data-ttu-id="7d500-104">Um zu überprüfen, ob die schemaerweiterung erfolgreich in Ihrer Active Directory-Domänendienste-Gesamtstruktur repliziert wurden, führen Sie folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="7d500-104">To verify that the schema extension have been successfully replicated in your Active Directory Domain Services forest, do the following:</span></span>
  
1. <span data-ttu-id="7d500-105">Melden Sie sich an einem Domänencontroller (mit Ausnahme der Domänencontroller, der die Schemamasterrolle enthält) in Ihrer Active Directory-Domänendienste-Gesamtstruktur, in dem durch die schemaerweiterungen, als Mitglied der Gruppe Organisations-Admins angewendet wurden an.</span><span class="sxs-lookup"><span data-stu-id="7d500-105">Log on to a domain controller (other than the domain controller that holds the schema master role) in your Active Directory Domain Services forest, where the schema extensions were applied as a member of the Enterprise Admins group.</span></span>
    
2. <span data-ttu-id="7d500-106">Open ADSI-Editor: Klicken Sie auf **Start**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **ADSI-Bearbeitung**.</span><span class="sxs-lookup"><span data-stu-id="7d500-106">Open ADSI Edit: Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="7d500-107">Alternativ klicken Sie auf **Start**und dann auf **Ausführen**, **adsiedit.msc** eingeben, starten Sie ADSI Edit.</span><span class="sxs-lookup"><span data-stu-id="7d500-107">Alternatively, click **Start**, then click **Run**, type **adsiedit.msc** to start ADSI Edit.</span></span>
  
3. <span data-ttu-id="7d500-108">Erweitern Sie in der Microsoft Management Console (MMC), wenn es nicht bereits aktiviert ist, klicken Sie auf ADSI-Bearbeitung.</span><span class="sxs-lookup"><span data-stu-id="7d500-108">In the Microsoft Management Console (MMC) tree, if it is not already selected, click ADSI Edit.</span></span>
    
4. <span data-ttu-id="7d500-109">Klicken Sie im Menü **Aktion** auf **Verbinden mit**.</span><span class="sxs-lookup"><span data-stu-id="7d500-109">On the **Action** menu, click **Connect to**.</span></span>
    
5. <span data-ttu-id="7d500-110">Wählen Sie im Dialogfeld **Verbindungseinstellungen** unter **Bekannten Namenskontext auswählen** die Option **Schema** aus und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="7d500-110">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>
    
6. <span data-ttu-id="7d500-111">Suchen Sie unter dem Schemacontainer nach CN=ms-RTC-SIP-SchemaVersion.</span><span class="sxs-lookup"><span data-stu-id="7d500-111">Under the schema container, search for CN=ms-RTC-SIP-SchemaVersion.</span></span> <span data-ttu-id="7d500-112">Wenn dieses Objekt vorhanden ist, und der Wert des **RangeUpper** -Attributs 1150 und der Wert des Attributs **RangeLower** 3 ist, wurde klicken Sie dann das Schema erfolgreich aktualisiert und repliziert.</span><span class="sxs-lookup"><span data-stu-id="7d500-112">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, then the schema was successfully updated and replicated.</span></span> <span data-ttu-id="7d500-113">Wenn dieses Objekt nicht vorhanden ist oder wenn die Werte der Attribute **RangeUpper** und **RangeLower** nicht als sind angegeben, klicken Sie dann das Schema nicht geändert wurde oder nicht repliziert wurde.</span><span class="sxs-lookup"><span data-stu-id="7d500-113">If this object does not exist or if the values of the **rangeUpper** and **rangeLower** attributes are not as specified, then the schema was not modified or has not replicated.</span></span>
    
> [!NOTE]
> <span data-ttu-id="7d500-114">Wenn die Kontrollkästchen der Replikation des Schemas eine erfolgreiche Replikation noch nicht angezeigt wird, warten Sie etwa 15 Minuten und dann erneut.</span><span class="sxs-lookup"><span data-stu-id="7d500-114">If your check of the replication of the schema does not yet show a successful replication, wait approximately 15 minutes and then check again.</span></span> <span data-ttu-id="7d500-115">Active Directory-Replikation wird basierend auf einem Modell lose Konsistenz und einige Replikationslatenz auftreten kann, basierend auf einer Reihe von Faktoren in den Server- und Infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="7d500-115">Active Directory replication is based on a loose consistency model and some replication latency can occur, based on a number of factors in the server and infrastructure.</span></span> 
  

