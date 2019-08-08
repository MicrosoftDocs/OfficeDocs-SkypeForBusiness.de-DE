---
title: Installieren der Dateien für den Vermittlungsserver in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die Dateien für den Vermittlungsserver in Skype for Business Server installieren.'
ms.openlocfilehash: b73832586ba4a09cc51f67bddcaf30c2f85fcca1
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240297"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a><span data-ttu-id="381fc-103">Installieren der Dateien für den Vermittlungsserver in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="381fc-103">Install the files for Mediation Server in Skype for Business Server</span></span>
 
<span data-ttu-id="381fc-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie die Dateien für den Vermittlungsserver in Skype for Business Server installieren.</span><span class="sxs-lookup"><span data-stu-id="381fc-104">**Summary:** Learn how to install the files for Mediation Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="381fc-105">Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie mindestens als lokaler Administrator beim Server angemeldet sein und ein Domänenbenutzerkonto verwenden, das mindestens Mitglied der Gruppe „RTCUniversalReadOnlyAdmins“ ist.</span><span class="sxs-lookup"><span data-stu-id="381fc-105">To successfully complete this procedure, you should be logged on to the server, at the minimum, as a local administrator and a domain user who has membership in at least the RTCUniversalReadOnlyAdmins group.</span></span>
  
<span data-ttu-id="381fc-106">Führen Sie die Schritte in diesem Thema aus, um den Assistenten für die Bereitstellung von Skype for Business Server auszuführen, um die Dateien für den Vermittlungsserver auf einem Computer zu installieren, den Sie einem vermittlungsserverpool hinzugefügt haben, nachdem Sie den Pool mithilfe des Topologie-Generators definiert und veröffentlicht haben.</span><span class="sxs-lookup"><span data-stu-id="381fc-106">Use the steps in this topic to run Skype for Business Server Deployment Wizard to install the files for Mediation Server on a computer that you added to a Mediation Server pool after you have used Topology Builder to define and publish the pool.</span></span> <span data-ttu-id="381fc-107">Wenn Sie den Mediationsserver für Dateien installieren, können Sie auch das für jeden Computer in einem vermittlungsserverpool erforderliche Zertifikat installieren und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="381fc-107">When installing files Mediation Server, you also install and assign the certificate required by each computer in a Mediation Server pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="381fc-108">In diesem Thema wird davon ausgegangen, dass Sie bereits einen eigenständigen vermittlungsserverpool in Ihrer Topologie definiert und veröffentlicht haben, wie unter [Bereitstellen eines Vermittlungsservers im Topologie-Generator in Skype for Business Server](deploy-a-mediation-server.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="381fc-108">This topic assumes that you have already defined and published a stand-alone Mediation Server pool in your topology, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md).</span></span> 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a><span data-ttu-id="381fc-109">So installieren Sie die Dateien für einen eigenständigen Vermittlungsserverpool</span><span class="sxs-lookup"><span data-stu-id="381fc-109">To install the files for a stand-alone Mediation Server pool</span></span>

1. <span data-ttu-id="381fc-110">Klicken Sie auf dem Installationsmedium mit der rechten Maustaste auf _ \<Installationsmedien\> _ **\Setup\amd64\Setup.exe**, und klicken Sie dann auf **als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="381fc-110">From the installation media, right-click  _\<installation media\>_ **\Setup\amd64\Setup.exe**, and then click **Run as Administrator**.</span></span>
    
2. <span data-ttu-id="381fc-111">Klicken Sie auf der Seite **Installationsspeicherort** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="381fc-111">On the **Installation Location** page, click **OK**.</span></span>
    
3. <span data-ttu-id="381fc-p102">Klicken Sie auf der Seite **Endbenutzer-Lizenzvertrag** auf **Ich stimme zu** und klicken Sie anschließend auf **OK**. (Dieser Schritt ist erforderlich, um fortfahren zu können.)</span><span class="sxs-lookup"><span data-stu-id="381fc-p102">On the **End User License Agreement** page, click **I accept**, and then click **OK**. (Required to continue.)</span></span>
    
4. <span data-ttu-id="381fc-114">Klicken Sie auf der Seite des **Skype for Business Server** -Bereitstellungs-Assistenten auf **Skype for Business Server System installieren oder aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="381fc-114">On the **Skype for Business Server Deployment Wizard** page, click **Install or Update Skype for Business Server System**.</span></span>
    
5. <span data-ttu-id="381fc-115">Klicken Sie neben **Schritt 1: Lokalen Konfigurationsspeicher installieren** auf **Ausführen** und folgen Sie den Anweisungen auf dem Bildschirm.</span><span class="sxs-lookup"><span data-stu-id="381fc-115">Next to **Step 1: Install Local Configuration Store**, click **Run**, and then follow the instructions on the screen.</span></span>
    
6. <span data-ttu-id="381fc-116">Übernehmen Sie auf der Seite **Lokales Replikat des zentralen Verwaltungsspeichers konfigurieren** die Standardeinstellung **Direkt aus zentralem Verwaltungsspeicher abrufen** und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="381fc-116">On the **Configure Local Replica of Central Management Store** page, accept the default **Retrieve directly from the Central Management Store**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="381fc-117">Wenn der Taskstatus auf der Seite **Befehle ausführen** als **Abgeschlossen** angezeigt wird, klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="381fc-117">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
8. <span data-ttu-id="381fc-118">Klicken Sie neben **Schritt 2: Einrichten oder Entfernen von Skype for Business Server-Komponenten**auf **Ausführen**, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="381fc-118">Next to **Step 2: Setup or Remove Skype for Business Server Components**, click **Run**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="381fc-119">Wenn der Taskstatus auf der Seite **Befehle ausführen** als **Abgeschlossen** angezeigt wird, klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="381fc-119">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
10. <span data-ttu-id="381fc-p103">Klicken Sie neben **Schritt 3: Zertifikate anfordern, installieren oder zuweisen** auf **Ausführen**. Folgen Sie den Anweisungen auf dem Bildschirm und übernehmen Sie die Standardeinstellungen. Da der Vermittlungsserver ein Zertifikat benötigt, müssen Sie **Schritt 3** zweimal ausführen: einmal zum Ausstellen und noch einmal zum Zuweisen des erforderlichen Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="381fc-p103">Next to **Step 3: Request, Install or Assign Certificates**, click **Run**. Follow the instructions on the screen, accepting the default settings. The Mediation Server requires one certificate, and so you will run **Step 3** twice: once to issue the required certificate, and once more to assign it.</span></span>
    
11. <span data-ttu-id="381fc-123">Wenn das Zertifikat ordnungsgemäß ausgestellt und zugewiesen wurde, klicken Sie neben **Schritt 4: Dienste starten** auf **Ausführen** und folgen Sie den Anweisungen auf dem Bildschirm.</span><span class="sxs-lookup"><span data-stu-id="381fc-123">When the certificate has been issued and assigned correctly, beside **Step 4: Start Services**, click **Run**, and then follow the instructions on the screen.</span></span>
    
12. <span data-ttu-id="381fc-124">Wenn **Schritt 4** erfolgreich abgeschlossen wurde, starten Sie den Server neu und melden Sie sich als Mitglied der Gruppe „Domänen-Admins“ an.</span><span class="sxs-lookup"><span data-stu-id="381fc-124">When **Step 4** has completed successfully, restart the server, and log on to the server as a member of the DomainAdmins group.</span></span>
    
13. <span data-ttu-id="381fc-125">Überprüfen Sie auf dem Computer, auf dem Sie die Skype for Business Server-Systemsteuerung ausführen, auf der Seite **Topologie** des Skype for Business Server Control Panels, dass der Dienststatus des Vermittlungsservers als grünes Häkchen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="381fc-125">On the computer where you are running Skype for Business Server Control Panel, verify on the **Topology** page of Skype for Business Server Control Panel that the service status of the Mediation Server is shown as a green check mark.</span></span> <span data-ttu-id="381fc-126">Wenn ein rotes X angezeigt wird, wählen Sie den Vermittlungsserver aus.</span><span class="sxs-lookup"><span data-stu-id="381fc-126">If a red X appears instead, select the Mediation Server.</span></span> <span data-ttu-id="381fc-127">Klicken Sie im Menü **Aktion** auf **Alle Dienste starten**.</span><span class="sxs-lookup"><span data-stu-id="381fc-127">On the **Action** menu, click **Start All Services**.</span></span> 
    
<span data-ttu-id="381fc-128">Wenn Sie dem vermittlungsserverpool mehr als einen Computer hinzugefügt haben, führen Sie die Schritte in diesem Verfahren auf allen anderen Computern im vermittlungsserverpool aus.</span><span class="sxs-lookup"><span data-stu-id="381fc-128">If you added more than one computer to the Mediation Server pool, perform the steps in this procedure on all other computers in the Mediation Server pool.</span></span> <span data-ttu-id="381fc-129">Wenn Sie keine Dateien für den Vermittlungsserver für andere Computer installieren müssen, führen Sie die Verfahren unter [Konfigurieren von Trunks in Skype for Business Server](configure-trunks.md) aus, um die Einstellungen für die trunk-Verbindung zwischen diesem vermittlungsserverpool zu konfigurieren (oder aller Mediation Server an einer Website) und deren Peer.</span><span class="sxs-lookup"><span data-stu-id="381fc-129">If you do not need to install files for Mediation Server for any other computers, then follow the procedures in [Configure trunks in Skype for Business Server](configure-trunks.md) to configure settings for the trunk connection between this Mediation Server pool (or all Mediation Servers at a site) and its peer.</span></span>

