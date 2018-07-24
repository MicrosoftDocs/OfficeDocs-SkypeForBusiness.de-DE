---
title: Erstellen eines Administrators für beständigen Chat in Skype for Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: 'Zusammenfassung: Lesen Sie in diesem Thema erfahren, wie eine Administratorrolle für Persistent Chat Server zum Aktivieren von anfängliche Konfiguration und Verwaltung von Persistent Chat-Dienste in Skype für Business Server 2015 zu erstellen.'
ms.openlocfilehash: df2c62964d6c1d315f6fda04132c829d235e6038
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20966115"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a><span data-ttu-id="4322f-103">Erstellen eines Administrators für beständigen Chat in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4322f-103">Create a Persistent Chat administrator in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4322f-104">**Zusammenfassung:** Lesen Sie in diesem Thema erfahren, wie eine Administratorrolle für Persistent Chat Server zum Aktivieren von anfängliche Konfiguration und Verwaltung von Persistent Chat-Dienste in Skype für Business Server 2015 zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4322f-104">**Summary:** Read this topic to learn how to create a Persistent Chat Server administrator role to enable initial configuration and management of Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="4322f-105">In Skype für Business Server müssen Benutzer, die bestimmte Aufgaben als Mitglieder von einer oder mehreren bestimmten Gruppen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="4322f-105">In Skype for Business Server, users who perform specific tasks must be assigned as members of one or more specific groups.</span></span> <span data-ttu-id="4322f-106">Role-Based Access Control (RBAC) wird verwendet, um Berechtigungen gewähren, indem Sie die Zuweisung von Benutzern zu vordefinierten Skype für Business Server Administratorrollen.</span><span class="sxs-lookup"><span data-stu-id="4322f-106">Role-Based Access Control (RBAC) is used to grant privileges by assigning users to predefined Skype for Business Server administrative roles.</span></span> <span data-ttu-id="4322f-107">Diese Rollen entsprechen den allgemeinen Sicherheitsgruppen in den Active Directory-Domänendiensten.</span><span class="sxs-lookup"><span data-stu-id="4322f-107">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="4322f-108">Mitglied der Sicherheitsgruppe Persistent Chat Administrator Rolle "cspersistentchatadministrator", werden die Cmdlets Persistent Chat Server Zugriff auf die Verwendung der Skype für Business Server-Verwaltungsshell oder die Skype für Unternehmen ausgeführt werden können Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="4322f-108">Members of the Persistent Chat Administrator security group, CsPersistentChatAdministrator, are granted access to the Persistent Chat Server cmdlets, which can be executed using either the Skype for Business Server Management Shell or the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="4322f-109">Bevor Sie den Server für beständigen Chat konfigurieren und verwalten, sollten Sie sicherstellen, dass die entsprechenden Rechte und Berechtigungen vorhanden sind und dass alle Benutzer, die als Administratoren für den beständigen Chat fungieren sollen, der Administrator-Sicherheitsgruppe für den beständigen Chat hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="4322f-109">Before configuring and administering Persistent Chat Server, be sure that the appropriate user rights and permissions are in place, and that any users who will act as Persistent Chat administrators are added to the Persistent Chat Administrator security group.</span></span>
  
> [!NOTE] 
> <span data-ttu-id="4322f-110">Beständiger Chat wird steht in Skype für Business Server 2015 jedoch nicht mehr unterstützt in Skype Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="4322f-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="4322f-111">Die gleiche Funktionalität ist in Teams verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4322f-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="4322f-112">Weitere Informationen finden Sie unter [Weg von Skype für Unternehmen, die Microsoft-Teams](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="4322f-112">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="4322f-113">Wenn Sie Persistent Chat verwenden müssen, sind Ihrer Auswahl an Benutzer, die diese Funktionalität Teams migrieren oder weiterhin Skype für Business Server 2015 verwenden.</span><span class="sxs-lookup"><span data-stu-id="4322f-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

## <a name="create-a-persistent-chat-administrator"></a><span data-ttu-id="4322f-114">Erstellen eines Administrators für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="4322f-114">Create a Persistent Chat administrator</span></span>

<span data-ttu-id="4322f-115">Führen Sie zum Hinzufügen eines Benutzers zur Persistent Chat Administrator-Sicherheitsgruppe Rolle "cspersistentchatadministrator", die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="4322f-115">To add a user to the Persistent Chat Administrator security group, CsPersistentChatAdministrator, perform the following steps:</span></span>
  
1. <span data-ttu-id="4322f-116">Melden Sie sich über ein Konto mit Berechtigung zum Ändern der Mitgliedschaft einer Active Directory-Gruppe an dem Computer an, auf dem „Active Directory-Benutzer und -Computer“ installiert ist.</span><span class="sxs-lookup"><span data-stu-id="4322f-116">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers have been installed.</span></span>
    
2. <span data-ttu-id="4322f-117">Klicken Sie nacheinander auf Start, Alle Programme, Verwaltung und Active Directory-Benutzer und -Computer.</span><span class="sxs-lookup"><span data-stu-id="4322f-117">Click Start, click All Programs, click Administrative Tools, and then click Active Directory Users and Computers.</span></span>
    
3. <span data-ttu-id="4322f-118">Erweitern Sie in „Active Directory-Benutzer und -Computer“ den Namen Ihrer Domäne und klicken Sie auf den Container „Users“.</span><span class="sxs-lookup"><span data-stu-id="4322f-118">In Active Directory Users and Computers, expand the name of your domain and click the Users container.</span></span>
    
4. <span data-ttu-id="4322f-119">Klicken Sie mit der rechten Maustaste auf die Sicherheitsgruppe „CsPersistentChatAdministrator“ und dann auf „Eigenschaften“.</span><span class="sxs-lookup"><span data-stu-id="4322f-119">Right-click the security group CsPersistentChatAdministrator, and then click Properties.</span></span>
    
5. <span data-ttu-id="4322f-120">Klicken Sie im Dialogfeld „Eigenschaften“auf die Registerkarte „Mitglieder“ und anschließend auf „Hinzufügen“.</span><span class="sxs-lookup"><span data-stu-id="4322f-120">In the Properties dialog box, on the Members tab, click Add.</span></span>
    
6. <span data-ttu-id="4322f-121">Geben Sie im Dialogfeld „Benutzer, Computer, Kontakte oder Gruppen auswählen“ im Feld „Geben Sie die zu verwendenden Objektnamen ein“ den Benutzer- oder Anzeigenamen des Benutzers ein, der zur Gruppe hinzugefügt werden soll, und klicken Sie auf „OK“.</span><span class="sxs-lookup"><span data-stu-id="4322f-121">In the Select Users, Computers, Contact, or Groups dialog box, type the user name or display name of the user to be added to the group in the Enter the object names to select box and then click OK.</span></span>
    
7. <span data-ttu-id="4322f-122">Klicken Sie im Dialogfeld „Eigenschaften“ auf „OK“.</span><span class="sxs-lookup"><span data-stu-id="4322f-122">In the Properties dialog box, click OK.</span></span>
    

