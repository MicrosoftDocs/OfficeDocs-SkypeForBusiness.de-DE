---
title: Erstellen von Administratoren für die Skype for Business Server-Systemsteuerung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainCreateCSCPAdmin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3312926a-4671-4030-bb92-90ac24c778dd
description: 'Um Zugriff auf die Skype für Business Server 2015 gewähren möchten, führen Sie folgende Schritte aus:'
ms.openlocfilehash: 7d4e536eee0741464a28f591b249491d4d528562
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33911100"
---
# <a name="create-skype-for-business-server-control-panel-administrators"></a><span data-ttu-id="58cb9-103">Erstellen von Administratoren für die Skype for Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="58cb9-103">Create Skype for Business Server Control Panel Administrators</span></span>
 
<span data-ttu-id="58cb9-104">Um Zugriff auf die Skype für Business Server 2015 gewähren möchten, führen Sie folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="58cb9-104">To grant access to the Skype for Business Server 2015, do the following:</span></span>
  
1. <span data-ttu-id="58cb9-105">Melden Sie sich als Mitglied der Gruppe „Domänen-Admins“ oder „RTCUniversalServerAdmins“ an.</span><span class="sxs-lookup"><span data-stu-id="58cb9-105">Log on as a member of the Domain Admins group or the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="58cb9-106">Öffnen Sie **Active Directory-Benutzer und -Computer**, erweitern Sie Ihre Domäne, klicken Sie mit der rechten Maustaste auf den Container **Benutzer** und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="58cb9-106">Open **Active Directory Users and Computers**, expand your domain, right-click the **Users** container, and then click **Properties**.</span></span>
    
3. <span data-ttu-id="58cb9-107">Klicken Sie im Fenster **CSAdministrator-Eigenschaften** auf die Registerkarte **Mitglieder**.</span><span class="sxs-lookup"><span data-stu-id="58cb9-107">In **CSAdministrator Properties**, click the **Members** tab.</span></span>
    
4. <span data-ttu-id="58cb9-p101">Klicken Sie auf der Registerkarte „Mitglieder“ auf **Hinzufügen**. Wechseln Sie unter **Benutzer, Kontakte, Computer, Dienstkonten oder Gruppen auswählen** zur Option **Geben Sie die zu verwendenden Objektnamen ein**. Geben Sie die Benutzer- bzw. Gruppennamen ein, die zur Gruppe „CSAdministrators“ hinzugefügt werden sollen. Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="58cb9-p101">On the Members tab, click **Add**. In **Select Users, Contacts, Computers, Service Accounts, or Groups**, locate the **Enter the object names to select**. Type the user name(s) or group name(s) to add to the group CSAdministrators. Click **OK**.</span></span>
    
5. <span data-ttu-id="58cb9-p102">Überprüfen Sie auf der Registerkarte „Mitglieder“, ob die ausgewählten Benutzer bzw. Gruppen vorhanden sind. Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="58cb9-p102">On the Members tab, confirm that the users or groups that you selected are present. Click **OK**.</span></span>
    
> [!TIP]
> <span data-ttu-id="58cb9-114">Die Skype Business Server-Systemsteuerung ist ein rollenbasierten.</span><span class="sxs-lookup"><span data-stu-id="58cb9-114">The Skype for Business Server Control Panel is a role-based access control tool.</span></span> <span data-ttu-id="58cb9-115">Die Mitgliedschaft in der Gruppe csadministrator hinzu ermöglicht einem Benutzer, der Skype für Business Server-Systemsteuerung Vollzugriff auf alle verfügbaren Konfigurationsfunktionen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="58cb9-115">Membership in the CsAdministrator group gives a user who is using the Skype for Business Server Control Panel full control for all the configuration functions available.</span></span> <span data-ttu-id="58cb9-116">Es sind weitere Rollen verfügbar, die für spezifische Funktionen konzipiert sind.</span><span class="sxs-lookup"><span data-stu-id="58cb9-116">There are other roles available that are designed for specific functions.</span></span> <span data-ttu-id="58cb9-117">Benutzer müssen nicht für Skype für Business Server aktiviert sein, damit die Mitglieder der Verwaltungsgruppen vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="58cb9-117">Users do not have to be enabled for Skype for Business Server in order to be made members of the management groups.</span></span> 
  
<span data-ttu-id="58cb9-118">Andere Rollen umfassen:</span><span class="sxs-lookup"><span data-stu-id="58cb9-118">Other roles include:</span></span>
  
- <span data-ttu-id="58cb9-119">**CsArchiving:** Mitglieder dieser Gruppe können alle Archivierungsfunktionen wie konfigurieren und Verwalten der Archivierungsserver-Rolle ausführen.</span><span class="sxs-lookup"><span data-stu-id="58cb9-119">**CsArchiving:** Members of this group can perform all archiving functions, such as configuring and managing the Archiving Server role.</span></span>
    
- <span data-ttu-id="58cb9-p104">**CsHelpDesk:** Mitglieder dieser Gruppe können die Konfiguration und Bereitstellung einschließlich Benutzereigenschaften und Richtlinien anzeigen. Mitglieder können zudem bestimmte Problembehandlungsaufgaben ausführen.</span><span class="sxs-lookup"><span data-stu-id="58cb9-p104">**CsHelpDesk:** Members of this group can view the configuration and deployment, including user properties and policies. Members can also perform specific troubleshooting tasks.</span></span>
    
- <span data-ttu-id="58cb9-p105">**CsLocationAdministrator:** Mitglieder verfügen über die niedrigste Berechtigungsstufe für die E9-1-1-Verwaltung. Sie können E9-1-1-Standorte und Netzwerk-IDs erstellen und in der Bereitstellung zuordnen.</span><span class="sxs-lookup"><span data-stu-id="58cb9-p105">**CsLocationAdministrator:** Members have the lowest level of user rights associated with Enhanced 9-1-1 (E9-1-1) management. They can create E9-1-1 locations and network identifiers and associate those in the deployment.</span></span>
    
- <span data-ttu-id="58cb9-124">**CsResponseGroupAdministrator:** Mitglieder können den Reaktionsgruppendienst verwalten und konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="58cb9-124">**CsResponseGroupAdministrator:** Members can manage and configure the Response Group service.</span></span>
    
- <span data-ttu-id="58cb9-125">**CsServerAdministrator:** Mitglieder können verwalten, überwachen und beheben alle Server mit Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="58cb9-125">**CsServerAdministrator:** Members can manage, monitor, and troubleshoot all servers running Skype for Business Server.</span></span>
    
- <span data-ttu-id="58cb9-126">**CsUserAdministrator:** Mitglieder können Benutzer verwalten, aktivieren und deaktivieren sowie vorhandene Richtlinien Benutzern zuweisen.</span><span class="sxs-lookup"><span data-stu-id="58cb9-126">**CsUserAdministrator:** Members can manage, enable and disable users, and assign existing policies to users.</span></span>
    
- <span data-ttu-id="58cb9-127">**CsViewOnlyAdministrator:** Mitglieder können die Bereitstellung und Konfiguration der Serverinformationen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="58cb9-127">**CsViewOnlyAdministrator:** Members can view the deployment and configuration of the server information.</span></span> <span data-ttu-id="58cb9-128">Diese Mitgliedschaft ermöglicht Mitglied, um die Integrität der von den Servern mit Skype für Business Server 2015 zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="58cb9-128">This membership enables a member to monitor the health of the servers running Skype for Business Server 2015.</span></span>
    
- <span data-ttu-id="58cb9-129">**"Csvoiceadministrator":** Mitglieder können erstellen, konfigurieren und Verwalten von VoIP-bezogene Einstellungen in Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="58cb9-129">**CsVoiceAdministrator:** Members can create, configure, and manage voice-related settings in Skype for Business Server.</span></span>
    
<span data-ttu-id="58cb9-130">Um die Aufrechterhaltung von Sicherheit und Integrität der rollenbasierten-Steuerelement, Hinzufügen von Benutzern zu Gruppen, die definieren, welche Rolle der Benutzer bei der Verwaltung der der Skype für Business Server-Bereitstellung ausführt.</span><span class="sxs-lookup"><span data-stu-id="58cb9-130">To help retain security and role-based access control integrity, add users to the groups that define what role the user performs in management of the Skype for Business Server deployment.</span></span>
  

