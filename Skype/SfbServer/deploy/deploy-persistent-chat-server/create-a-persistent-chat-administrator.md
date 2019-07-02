---
title: Erstellen eines Administrators für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: 'Zusammenfassung: Lesen Sie dieses Thema, um zu erfahren, wie Sie eine Server Administratorrolle für beständigen Chat erstellen, um die anfängliche Konfiguration und Verwaltung beständiger Chat Dienste in Skype for Business Server 2015 zu ermöglichen.'
ms.openlocfilehash: b0edd3e1f10bf040be18242bfa600bb694169257
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418143"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a><span data-ttu-id="51a2b-103">Erstellen eines Administrators für beständigen Chat in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="51a2b-103">Create a Persistent Chat administrator in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="51a2b-104">**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie eine Server Administratorrolle für beständigen Chat erstellen, um die anfängliche Konfiguration und Verwaltung beständiger Chat Dienste in Skype for Business Server 2015 zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="51a2b-104">**Summary:** Read this topic to learn how to create a Persistent Chat Server administrator role to enable initial configuration and management of Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="51a2b-105">In Skype for Business Server müssen Benutzer, die bestimmte Aufgaben ausführen, Mitgliedern einer oder mehrerer bestimmter Gruppen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="51a2b-105">In Skype for Business Server, users who perform specific tasks must be assigned as members of one or more specific groups.</span></span> <span data-ttu-id="51a2b-106">Rollenbasierte Zugriffssteuerung wird verwendet, um Berechtigungen zu gewähren, indem Benutzer vordefinierten Skype for Business Server-Administratorrollen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="51a2b-106">Role-Based Access Control (RBAC) is used to grant privileges by assigning users to predefined Skype for Business Server administrative roles.</span></span> <span data-ttu-id="51a2b-107">Diese Rollen entsprechen den allgemeinen Sicherheitsgruppen in den Active Directory-Domänendiensten.</span><span class="sxs-lookup"><span data-stu-id="51a2b-107">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="51a2b-108">Mitgliedern der Gruppe "beständiger Chat-Administrator", CsPersistentChatAdministrator, wird der Zugriff auf die Server-Cmdlets des beständigen Chats gewährt, die entweder über die Skype for Business Server-Verwaltungsshell oder über Skype for Business ausgeführt werden können. Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="51a2b-108">Members of the Persistent Chat Administrator security group, CsPersistentChatAdministrator, are granted access to the Persistent Chat Server cmdlets, which can be executed using either the Skype for Business Server Management Shell or the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="51a2b-109">Bevor Sie den Server für beständigen Chat konfigurieren und verwalten, sollten Sie sicherstellen, dass die entsprechenden Rechte und Berechtigungen vorhanden sind und dass alle Benutzer, die als Administratoren für den beständigen Chat fungieren sollen, der Administrator-Sicherheitsgruppe für den beständigen Chat hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="51a2b-109">Before configuring and administering Persistent Chat Server, be sure that the appropriate user rights and permissions are in place, and that any users who will act as Persistent Chat administrators are added to the Persistent Chat Administrator security group.</span></span>
  
> [!NOTE] 
> <span data-ttu-id="51a2b-110">Der beständige Chat ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="51a2b-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="51a2b-111">In Teams steht dieselbe Funktionalität zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="51a2b-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="51a2b-112">Weitere Informationen finden Sie unter [Erste Schritte mit dem Upgrade für Microsoft Teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="51a2b-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="51a2b-113">Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktion für Teams benötigen, oder die Verwendung von Skype for Business Server 2015 fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="51a2b-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

## <a name="create-a-persistent-chat-administrator"></a><span data-ttu-id="51a2b-114">Create a Persistent Chat administrator</span><span class="sxs-lookup"><span data-stu-id="51a2b-114">Create a Persistent Chat administrator</span></span>

<span data-ttu-id="51a2b-115">Führen Sie die folgenden Schritte aus, um einen Benutzer zur Administrator Sicherheitsgruppe für beständigen Chat hinzuzufügen: CsPersistentChatAdministrator</span><span class="sxs-lookup"><span data-stu-id="51a2b-115">To add a user to the Persistent Chat Administrator security group, CsPersistentChatAdministrator, perform the following steps:</span></span>
  
1. <span data-ttu-id="51a2b-116">Melden Sie sich über ein Konto mit Berechtigung zum Ändern der Mitgliedschaft einer Active Directory-Gruppe an dem Computer an, auf dem „Active Directory-Benutzer und -Computer“ installiert ist.</span><span class="sxs-lookup"><span data-stu-id="51a2b-116">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers have been installed.</span></span>
    
2. <span data-ttu-id="51a2b-117">Klicken Sie nacheinander auf Start, Alle Programme, Verwaltung und Active Directory-Benutzer und -Computer.</span><span class="sxs-lookup"><span data-stu-id="51a2b-117">Click Start, click All Programs, click Administrative Tools, and then click Active Directory Users and Computers.</span></span>
    
3. <span data-ttu-id="51a2b-118">Erweitern Sie in „Active Directory-Benutzer und -Computer“ den Namen Ihrer Domäne und klicken Sie auf den Container „Users“.</span><span class="sxs-lookup"><span data-stu-id="51a2b-118">In Active Directory Users and Computers, expand the name of your domain and click the Users container.</span></span>
    
4. <span data-ttu-id="51a2b-119">Klicken Sie mit der rechten Maustaste auf die Sicherheitsgruppe „CsPersistentChatAdministrator“ und dann auf „Eigenschaften“.</span><span class="sxs-lookup"><span data-stu-id="51a2b-119">Right-click the security group CsPersistentChatAdministrator, and then click Properties.</span></span>
    
5. <span data-ttu-id="51a2b-120">Klicken Sie im Dialogfeld „Eigenschaften“auf die Registerkarte „Mitglieder“ und anschließend auf „Hinzufügen“.</span><span class="sxs-lookup"><span data-stu-id="51a2b-120">In the Properties dialog box, on the Members tab, click Add.</span></span>
    
6. <span data-ttu-id="51a2b-121">Geben Sie im Dialogfeld „Benutzer, Computer, Kontakte oder Gruppen auswählen“ im Feld „Geben Sie die zu verwendenden Objektnamen ein“ den Benutzer- oder Anzeigenamen des Benutzers ein, der zur Gruppe hinzugefügt werden soll, und klicken Sie auf „OK“.</span><span class="sxs-lookup"><span data-stu-id="51a2b-121">In the Select Users, Computers, Contact, or Groups dialog box, type the user name or display name of the user to be added to the group in the Enter the object names to select box and then click OK.</span></span>
    
7. <span data-ttu-id="51a2b-122">Klicken Sie im Dialogfeld „Eigenschaften“ auf „OK“.</span><span class="sxs-lookup"><span data-stu-id="51a2b-122">In the Properties dialog box, click OK.</span></span>
    

