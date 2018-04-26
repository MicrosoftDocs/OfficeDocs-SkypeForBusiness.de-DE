---
title: Hinzufügen von Archivierungsdatenbanken zu einer vorhandenen Bereitstellung in Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: 'Zusammenfassung: In diesem Themenbereich erfahren Sie, wie Sie Archivierungsdatenbanken zu Ihrer -Bereitstellung hinzufügen können.'
ms.openlocfilehash: 09185eed2a8bd0cc9b2a03fc6361abeadbd01829
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server-2015"></a><span data-ttu-id="1f8f8-103">Hinzufügen von Archivierungsdatenbanken zu einer vorhandenen Bereitstellung in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="1f8f8-103">Add archiving databases to an existing deployment in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="1f8f8-104">Zusammenfassung: In diesem Themenbereich erfahren Sie, wie Sie Archivierungsdatenbanken zu Ihrer -Bereitstellung hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="1f8f8-104">Summary: Read this topic to learn how to add archiving databases to your  deployment.</span></span>
  
<span data-ttu-id="1f8f8-105">Sie müssen die Archivierung in Ihre Topologie aufnehmen, bevor Sie Ihre Bereitstellung zur Unterstützung der Archivierung konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="1f8f8-105">You must incorporate archiving into your topology before you can configure your deployment to support archiving.</span></span> <span data-ttu-id="1f8f8-106">In diesem Thema wird erläutert, wie Sie das  für Folgendes verwenden:</span><span class="sxs-lookup"><span data-stu-id="1f8f8-106">The information in this topic explains how to use  to:</span></span>
  
- <span data-ttu-id="1f8f8-107">Hinzufügen einer Archivierungsdatenbank zu Ihrer Topologie</span><span class="sxs-lookup"><span data-stu-id="1f8f8-107">Add an archiving database to your topology.</span></span>
    
- <span data-ttu-id="1f8f8-108">Veröffentlichen der aktualisierten Topologie zum Hinzufügen der Archivierungsdatenbank zu Ihrer -Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="1f8f8-108">Publish the updated topology to add the archiving database to your  deployment.</span></span>
    
> [!NOTE]
> <span data-ttu-id="1f8f8-109">Wenn Sie die -Integration zum Speichern von Archivierungsdaten und -dateien auf -Servern für alle Benutzer in der Bereitstellung verwenden möchten, geben Sie nicht  oder  an.</span><span class="sxs-lookup"><span data-stu-id="1f8f8-109">If you want to use  integration to store archiving data and files on  servers for all your users in your deployment, do not specify  or  information.</span></span>
  
### <a name="add-an-archiving-database-to-your-topology"></a><span data-ttu-id="1f8f8-110">Hinzufügen einer Archivierungsdatenbank zu Ihrer Topologie</span><span class="sxs-lookup"><span data-stu-id="1f8f8-110">Add an archiving database to your topology</span></span>

1. <span data-ttu-id="1f8f8-111">Melden Sie sich auf einem Computer, auf dem  ausgeführt wird oder auf dem die -Verwaltungstools installiert sind, mit einem Konto an, das Mitglied der lokalen Gruppe „Benutzer“ ist (oder mit einem Konto mit äquivalenten Benutzerrechten).</span><span class="sxs-lookup"><span data-stu-id="1f8f8-111">On a computer that is running , or on which the  administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
2. <span data-ttu-id="1f8f8-112">Start Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="1f8f8-112">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="1f8f8-113">Navigieren Sie in der Konsolenstruktur zum Front-End-Pool, in dem die Archivierung bereitgestellt werden soll, und klicken Sie dann auf den Namen des entsprechenden Front-End-Pools.</span><span class="sxs-lookup"><span data-stu-id="1f8f8-113">In the console tree, navigate to the Front End pool in which you want to deploy Archiving, and then click the name of the Front End pool where you want to deploy archiving.</span></span>
    
4. <span data-ttu-id="1f8f8-114">Klicken Sie im Menü **Aktionen** auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="1f8f8-114">In the **Action** menu, click **Edit Properties**.</span></span> 
    
5. <span data-ttu-id="1f8f8-115">Klicken Sie im Dialogfeld **Eigenschaften bearbeiten** auf **Allgemein**.</span><span class="sxs-lookup"><span data-stu-id="1f8f8-115">In the **Edit Properties** dialog box, click **General**.</span></span>
    
6. <span data-ttu-id="1f8f8-116">Führen Sie einen Bildlauf nach unten zur **Archivierung** aus.</span><span class="sxs-lookup"><span data-stu-id="1f8f8-116">Scroll down to **Archiving**.</span></span>
    
7. <span data-ttu-id="1f8f8-117">Aktivieren Sie das Kontrollkästchen **Archivierung**.</span><span class="sxs-lookup"><span data-stu-id="1f8f8-117">Select the **Archiving** check box.</span></span>
    
8. <span data-ttu-id="1f8f8-118">Under **Archiving SQL Server store,** do one of the following:</span><span class="sxs-lookup"><span data-stu-id="1f8f8-118">Under **Archiving SQL Server store,** do one of the following:</span></span>
    
   - <span data-ttu-id="1f8f8-119">Zum Verwenden eines vorhandenen SQL Server-Speichers klicken Sie im Dropdown-Listenfeld auf den Namen des SQL Server-Speichers, den Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="1f8f8-119">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span> <span data-ttu-id="1f8f8-120">Wenn alle Benutzer in  oder höher verwaltet werden, können Sie die -Kommunikation für alle Benutzer  archivieren.</span><span class="sxs-lookup"><span data-stu-id="1f8f8-120">If all of your users are homed on  or above, you can archive  communications for all your users in .</span></span> <span data-ttu-id="1f8f8-121">In diesem Fall muss der -Archivierungsspeicher nicht konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="1f8f8-121">In this case, you don’t need to configure  Archiving store.</span></span>
    
   - <span data-ttu-id="1f8f8-122">Zum Angeben eines neuen SQL Server-Speichers klicken Sie auf **Neu** und gehen dann im Dialogfeld **Neuen SQL Server-Speicher definieren** wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="1f8f8-122">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server store** dialog box, do the following:</span></span>
    
   - <span data-ttu-id="1f8f8-123">Geben Sie im Feld SQL Server-FQDN den FQDN des Servers an, auf dem Sie den neuen -Speicher erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="1f8f8-123">In SQL Server FQDN, specify the FQDN of the server on which you want to create the new  store.</span></span>
    
   - <span data-ttu-id="1f8f8-124">Klicken Sie auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz** und geben Sie die Instanz an, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="1f8f8-124">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
    
   - <span data-ttu-id="1f8f8-125">Wenn sich die angegebene -Instanz in einer Spiegelungsbeziehung befindet, aktivieren Sie das Kontrollkästchen Diese SQL-Instanz befindet sich in einer Spiegelungsbeziehung und geben Sie dann im Feld Spiegelportnummer die Portnummer an.</span><span class="sxs-lookup"><span data-stu-id="1f8f8-125">If the specified  instance is in a mirroring relationship, select the This SQL instance is in mirroring relation check box, and then, in Mirror port number, specify the port number.</span></span>
    
9. <span data-ttu-id="1f8f8-126">If you want to use SQL Server store mirroring, select **Enable SQL Server Store mirroring**, and then do the following:</span><span class="sxs-lookup"><span data-stu-id="1f8f8-126">If you want to use SQL Server store mirroring, select **Enable SQL Server Store mirroring**, and then do the following:</span></span>
    
   - <span data-ttu-id="1f8f8-127">Zum Verwenden eines vorhandenen -Speichers zur Spiegelung klicken Sie im Dropdown-Listenfeld SQL Server-Speicherspiegel für Archivierung auf den Namen des -Speichers, den Sie für die Spiegelung verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="1f8f8-127">To use an existing  store for mirroring, in the Archiving SQL Server store mirror drop-down list box, click the name of the  store that you want to use for mirroring.</span></span>
    
   - <span data-ttu-id="1f8f8-128">Zum Angeben eines neuen -Speichers zur Spiegelung klicken Sie auf Neu und führen Sie dann im Dialogfeld Neuen SQL Server-Speicher definieren einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="1f8f8-128">To specify a new  store for mirroring, click New, and then in the Define New SQL Server Store dialog box, do one of the following:</span></span>
    
    <span data-ttu-id="1f8f8-129">a.</span><span class="sxs-lookup"><span data-stu-id="1f8f8-129">a.</span></span> <span data-ttu-id="1f8f8-130">Geben Sie in SQL-Server-FQDN den FQDN des Computers mit SQL Server an, auf dem Sie den neuen -Speicher erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="1f8f8-130">In SQL Server FQDN, specify the FQDN of the SQL Server on which you want to create the new  store.</span></span>
    
    <span data-ttu-id="1f8f8-131">b.</span><span class="sxs-lookup"><span data-stu-id="1f8f8-131">b.</span></span> <span data-ttu-id="1f8f8-132">Klicken Sie auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz** und geben Sie die Instanz an, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="1f8f8-132">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
    
    <span data-ttu-id="1f8f8-133">c.</span><span class="sxs-lookup"><span data-stu-id="1f8f8-133">c.</span></span> <span data-ttu-id="1f8f8-134">Wenn sich die angegebene -Instanz in einer Spiegelungsbeziehung befindet, aktivieren Sie das Kontrollkästchen Diese SQL-Instanz befindet sich in einer Spiegelungsbeziehung und geben Sie dann im Feld Spiegelportnummer die Portnummer an.</span><span class="sxs-lookup"><span data-stu-id="1f8f8-134">If the specified  instance is in a mirroring relationship, select the This SQL instance is in mirroring relation check box, and then, in Mirror port number, specify the port number.</span></span>
    
   - <span data-ttu-id="1f8f8-135">Wenn Sie die -Spiegelung aktivieren und einen -Spiegelungszeugen hinzufügen oder ändern möchten (eine dritte, separate -Instanz, die die Integrität des primären -Servers und der Spiegelinstanzen erkennen kann), aktivieren Sie das Kontrollkästchen Automatisches Failover mithilfe des SQL Server-Spiegelungszeugen aktivieren und führen Sie dann einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="1f8f8-135">If you enable  mirroring and want to add or change a  mirroring witness (a third, separate  instance that can detect the health of the primary  server and mirror instances), select the Use SQL Server mirroring witness to enable automatic failover check box, and then do one of the following:</span></span>
    
    <span data-ttu-id="1f8f8-136">a.</span><span class="sxs-lookup"><span data-stu-id="1f8f8-136">a.</span></span> <span data-ttu-id="1f8f8-137">Geben Sie im Feld SQL Server-FQDN den FQDN des Servers an, auf dem Sie den neuen -Spiegelungszeugen erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="1f8f8-137">In SQL Server FQDN, specify the FQDN of the server on which you want to create the new  mirroring witness.</span></span>
    
    <span data-ttu-id="1f8f8-138">b.</span><span class="sxs-lookup"><span data-stu-id="1f8f8-138">b.</span></span> <span data-ttu-id="1f8f8-139">Klicken Sie auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz** und geben Sie die Instanz an, die Sie für den Spiegelungszeugen verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="1f8f8-139">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
    
    <span data-ttu-id="1f8f8-140">c.</span><span class="sxs-lookup"><span data-stu-id="1f8f8-140">c.</span></span> <span data-ttu-id="1f8f8-141">Wenn sich die angegebene -Instanz in einer Spiegelungsbeziehung befindet, aktivieren Sie das Kontrollkästchen Diese SQL-Instanz befindet sich in einer Spiegelungsbeziehung und geben Sie dann im Feld Spiegelportnummer die Portnummer an.</span><span class="sxs-lookup"><span data-stu-id="1f8f8-141">If the specified  instance is in a mirroring relationship, select the This SQL instance is in mirroring relation check box, and then, in Mirror port number, specify the port number.</span></span>
    
10. <span data-ttu-id="1f8f8-142">Klicken Sie zum Speichern der Konfiguration auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1f8f8-142">To save the configuration, click **OK**.</span></span>
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a><span data-ttu-id="1f8f8-143">Veröffentlichen der aktualisierten Topologie zum Hinzufügen einer Archivierungsdatenbank zu Ihrer Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="1f8f8-143">Publish the updated topology to add an archiving database to your deployment</span></span>

1. <span data-ttu-id="1f8f8-144">Melden Sie sich bei einem Computer, der  ausführt oder auf dem die -Verwaltungstools installiert sind, mit einem Konto an, das Mitglied der lokalen Benutzergruppe ist (oder mit einem Konto mit entsprechenden Benutzerrechten).</span><span class="sxs-lookup"><span data-stu-id="1f8f8-144">On a computer that is running , or on which the  administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1f8f8-145">Sie können eine Topologie definieren, indem Sie ein Konto verwenden, das Mitglied der lokalen Benutzergruppe ist. Zum Veröffentlichen einer Topologie (Voraussetzung für das Hinzufügen eines Servers zur Topologie) müssen Sie ein Konto verwenden, das Mitglied der Gruppe Domänen-Admins und der Gruppe RTCUniversalServerAdmins ist und über Vollzugriff (Lesen, Schreiben und Ändern) für die Dateifreigabe verfügt, die Sie für den -Dateispeicher verwenden möchten, damit der  die erforderlichen DACLs (Discretionary Access Control Lists) konfigurieren kann. Alternativ dazu können Sie ein Konto mit äquivalenten Rechten verwenden.</span><span class="sxs-lookup"><span data-stu-id="1f8f8-145">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the Domain Admins group and the RTCUniversalServerAdmins group, and that has full control permissions (read, write, and modify) on the file share that you are using for the  file store (so that  can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="1f8f8-146">Öffnen Sie die Topologie, die Sie im vorigen Abschnitt mithilfe von  erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="1f8f8-146">Open the topology you created in the previous section using .</span></span>
    
3. <span data-ttu-id="1f8f8-147">Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf **** und dann auf **Topologie veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="1f8f8-147">In the console tree, right-click ****, and then click **Publish Topology**.</span></span>
    
4. <span data-ttu-id="1f8f8-148">Klicken Sie auf der Seite **Topologie veröffentlichen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="1f8f8-148">On the **Publish the topology** page, click **Next**.</span></span>
    
5. <span data-ttu-id="1f8f8-149">Stellen Sie auf der Seite **Datenbanken erstellen** sicher, dass die Datenbank ausgewählt ist, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="1f8f8-149">On the **Create databases** page, verify that the database is selected, and then click **Next**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="1f8f8-150">Wenn Sie nicht über die erforderlichen Berechtigungen zum Erstellen von Datenbanken verfügen, können Sie die Auswahl der Datenbank abbrechen, sodass ein Benutzer mit den erforderlichen Berechtigungen die Datenbankerstellung ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="1f8f8-150">If you do not have the appropriate permissions to create databases, you can cancel the selection of the database and someone with appropriate permissions can create the database.</span></span> <span data-ttu-id="1f8f8-151">Über den  können nur Datenbanken auf dedizierten SQL-Servern installiert werden.</span><span class="sxs-lookup"><span data-stu-id="1f8f8-151">Only databases on dedicated SQL Servers can be installed by using .</span></span> <span data-ttu-id="1f8f8-152">Datenbanken auf SQL-Servern, die gemeinsam mit anderen Serverkomponenten ausgeführt werden, müssen über das lokale Setup auf dem jeweiligen Computer installiert werden.</span><span class="sxs-lookup"><span data-stu-id="1f8f8-152">Databases on SQL Servers that are collocated with other server components must be installed by running local setup on that computer.</span></span> 
  
6. <span data-ttu-id="1f8f8-153">Vergewissern Sie sich auf der Seite **Assistent für die Veröffentlichung abgeschlossen**, dass die Topologie erfolgreich veröffentlicht wurde, und klicken Sie anschließend auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="1f8f8-153">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="1f8f8-154">Nach Veröffentlichung der Topologie müssen Sie Optionen und Richtlinien für die Archivierung konfigurieren, bevor Inhalte archiviert werden können.</span><span class="sxs-lookup"><span data-stu-id="1f8f8-154">After publishing the topology, you must configure options and policies for Archiving before any content can be archived.</span></span> <span data-ttu-id="1f8f8-155">For details, see [Configure archiving options for Skype for Business Server 2015](configure-archiving-options.md) and [Configure archiving policies for Skype for Business Server 2015](configure-archiving-policies.md).</span><span class="sxs-lookup"><span data-stu-id="1f8f8-155">For details, see [Configure archiving options for Skype for Business Server 2015](configure-archiving-options.md) and [Configure archiving policies for Skype for Business Server 2015](configure-archiving-policies.md).</span></span> 
  

