---
title: 'Lync Server 2013: authentifizierte Benutzerberechtigungen werden entfernt'
description: 'Lync Server 2013: authentifizierte Benutzerberechtigungen werden entfernt.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Authenticated user permissions are removed
ms:assetid: 5fcd70a5-813a-4076-9bb6-5b0d47505038
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398425(v=OCS.15)
ms:contentKeyID: 48184304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59da0ec893395405010afdd0263bd6be5d646881
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573021"
---
# <a name="authenticated-user-permissions-are-removed-in-lync-server-2013"></a><span data-ttu-id="5af46-103">Berechtigungen für authentifizierte Benutzer werden in lync Server 2013 entfernt.</span><span class="sxs-lookup"><span data-stu-id="5af46-103">Authenticated user permissions are removed in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5af46-104">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="5af46-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="5af46-105">In einer gesperrten Active Directory Umgebung werden authentifizierte Benutzerzugriffs Steuerungs Einträge (ACEs) aus den standardmäßigen Active Directory Containern entfernt, einschließlich der Benutzer, der Konfiguration oder des Systems sowie der Organisationseinheiten (Organizational Units, OUs), in denen Benutzer-und Computer Objekte gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="5af46-105">In a locked-down Active Directory environment, authenticated user access control entries (ACEs) are removed from the default Active Directory containers, including the Users, Configuration or System, and organizational units (OUs) where User and Computer objects are stored.</span></span> <span data-ttu-id="5af46-106">Durch das Entfernen authentifizierter Benutzer-ACEs wird der Lesezugriff auf Active Directory Informationen verhindert.</span><span class="sxs-lookup"><span data-stu-id="5af46-106">Removing authenticated user ACEs prevents read access to Active Directory information.</span></span> <span data-ttu-id="5af46-107">Das Entfernen der ACEs verursacht jedoch Probleme für lync Server 2013, da Sie von Leseberechtigungen für diese Container abhängt, damit Benutzer die Domänenvorbereitung ausführen können.</span><span class="sxs-lookup"><span data-stu-id="5af46-107">However, removing the ACEs creates issues for Lync Server 2013 because it depends on read permissions to these containers to allow users to run domain preparation.</span></span>

<span data-ttu-id="5af46-108">In diesem Fall erteilt die Mitgliedschaft in der Gruppe "Domänen-Admins", die zum Ausführen der Domänenvorbereitung, Serveraktivierung und Poolerstellung erforderlich ist, keinen Lesezugriff mehr auf Active Directory Informationen, die in den Standardcontainern gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="5af46-108">In this situation, membership in the Domain Admins group, which is required to run domain preparation, server activation, and pool creation, no longer grants read access to Active Directory information stored in the default containers.</span></span> <span data-ttu-id="5af46-109">Sie müssen Lesezugriff-Berechtigungen für verschiedene Container in der Gesamtstruktur-Stammdomäne manuell erteilen, um zu überprüfen, ob die Vorbereitungs Prozedur für die erforderliche Gesamtstruktur abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="5af46-109">You must manually grant read-access permissions on various containers in the forest root domain to check that the prerequisite forest preparation procedure is complete.</span></span>

<span data-ttu-id="5af46-110">Um einem Benutzer die Ausführung der Domänenvorbereitung, Serveraktivierung oder Poolerstellung in einer nicht-Gesamtstruktur-Stammdomäne zu ermöglichen, haben Sie die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="5af46-110">To enable a user to run domain preparation, server activation, or pool creation on any non-forest root domain, you have the following options:</span></span>

  - <span data-ttu-id="5af46-111">Verwenden Sie ein Konto, das Mitglied der Gruppe "Organisations-Admins" ist, um die Domänenvorbereitung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5af46-111">Use an account that is a member of the Enterprise Admins group to run domain preparation.</span></span>

  - <span data-ttu-id="5af46-112">Verwenden Sie ein Konto, das Mitglied der Gruppe "Domänen-Admins" ist, und erteilen Sie diesem Konto Lesezugriffsberechtigungen für jeden der folgenden Container in der Gesamtstruktur-Stammdomäne:</span><span class="sxs-lookup"><span data-stu-id="5af46-112">Use an account that is a member of the Domain Admins group and grant this account read-access permissions on each of the following containers in the forest root domain:</span></span>
    
      - <span data-ttu-id="5af46-113">Domäne</span><span class="sxs-lookup"><span data-stu-id="5af46-113">Domain</span></span>
    
      - <span data-ttu-id="5af46-114">Konfiguration oder System</span><span class="sxs-lookup"><span data-stu-id="5af46-114">Configuration or System</span></span>

<span data-ttu-id="5af46-115">Wenn Sie ein Konto, das Mitglied der Gruppe "Organisations-Admins" ist, zum Ausführen der Domänenvorbereitung oder anderer Setup Aufgaben nicht verwenden möchten, erteilen Sie dem Konto, für das Sie den Lesezugriff verwenden möchten, explizit die entsprechenden Container im Gesamtstrukturstamm.</span><span class="sxs-lookup"><span data-stu-id="5af46-115">If you do not want to use an account that is a member of the Enterprise Admins group to run domain preparation or other Setup tasks, explicitly grant the account you want to use read access on the relevant containers in the forest root.</span></span>

<div>

## <a name="to-give-users-read-access-permissions-on-containers-in-the-forest-root-domain"></a><span data-ttu-id="5af46-116">So erteilen Sie Benutzern Lesezugriffsberechtigungen für Container in der Gesamtstruktur-Stammdomäne</span><span class="sxs-lookup"><span data-stu-id="5af46-116">To give users read-access permissions on containers in the forest root domain</span></span>

1.  <span data-ttu-id="5af46-117">Melden Sie sich bei dem Computer, der der Gesamtstruktur-Stammdomäne angehört, mit einem Konto an, das Mitglied der Gruppe "Domänen-Admins" für die Gesamtstruktur-Stammdomäne ist.</span><span class="sxs-lookup"><span data-stu-id="5af46-117">Log on to the computer joined to the forest root domain with an account that is a member of the Domain Admins group for the forest root domain.</span></span>

2.  <span data-ttu-id="5af46-118">Führen Sie adsiedit. msc für die Gesamtstruktur-Stammdomäne aus.</span><span class="sxs-lookup"><span data-stu-id="5af46-118">Run adsiedit.msc for the forest root domain.</span></span>
    
    <span data-ttu-id="5af46-119">Wenn authentifizierte Benutzer-ACEs aus der Domäne, Konfiguration oder dem System Container entfernt wurden, müssen Sie dem Container schreibgeschützte Berechtigungen erteilen, wie in den folgenden Schritten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5af46-119">If authenticated user ACEs were removed from the Domain, Configuration, or System container, you must grant read-only permissions to the container, as described in the following steps.</span></span>

3.  <span data-ttu-id="5af46-120">Klicken Sie mit der rechten Maustaste auf den Container, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="5af46-120">Right-click the container, and then click **Properties**.</span></span>

4.  <span data-ttu-id="5af46-121">Klicken Sie auf die Registerkarte **Sicherheit**.</span><span class="sxs-lookup"><span data-stu-id="5af46-121">Click the **Security** tab.</span></span>

5.  <span data-ttu-id="5af46-122">Klicken Sie auf **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="5af46-122">Click **Advanced**.</span></span>

6.  <span data-ttu-id="5af46-123">Klicken Sie auf der Registerkarte **Berechtigungen** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="5af46-123">On the **Permissions** tab, click **Add**.</span></span>

7.  <span data-ttu-id="5af46-124">Geben Sie den Namen des Benutzers oder der Gruppe ein, der Berechtigungen erhält, indem Sie folgendes Format verwenden: `domain\account name` , und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5af46-124">Type the name of the user or group receiving permissions by using the following format: `domain\account name`, and then click **OK**.</span></span>

8.  <span data-ttu-id="5af46-125">Klicken Sie auf der Registerkarte **Objekte** unter **gilt für**auf **nur dieses Objekt**.</span><span class="sxs-lookup"><span data-stu-id="5af46-125">On the **Objects** tab, in **Applies To**, click **This Object Only**.</span></span>

9.  <span data-ttu-id="5af46-126">Wählen Sie unter **Berechtigungen**die folgenden ACEs zulassen aus, indem Sie auf die Spalte **zulassen** klicken: **Inhalt auflisten**, **alle Eigenschaften lesen**und **Berechtigungen Lesen**.</span><span class="sxs-lookup"><span data-stu-id="5af46-126">In **Permissions**, select the following Allow ACEs by clicking the **Allow** column: **List Content**, **Read All Properties**, and **Read Permissions**.</span></span>

10. <span data-ttu-id="5af46-127">Klicken Sie zweimal auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5af46-127">Click **OK** twice.</span></span>

11. <span data-ttu-id="5af46-128">Wiederholen Sie diese Schritte für alle in Schritt 2 aufgeführten relevanten Container.</span><span class="sxs-lookup"><span data-stu-id="5af46-128">Repeat these steps for any of the relevant containers listed in Step 2.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

