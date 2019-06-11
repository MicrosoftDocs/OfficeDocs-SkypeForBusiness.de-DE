---
title: 'Lync Server 2013: Entfernte Berechtigungen für authentifizierte Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Authenticated user permissions are removed
ms:assetid: 5fcd70a5-813a-4076-9bb6-5b0d47505038
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398425(v=OCS.15)
ms:contentKeyID: 48184304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d5e14b8129f771093ed9facb09d047ac7c36d32
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839900"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="authenticated-user-permissions-are-removed-in-lync-server-2013"></a><span data-ttu-id="1ea7d-102">Entfernte Berechtigungen für authentifizierte Benutzer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ea7d-102">Authenticated user permissions are removed in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ea7d-103">_**Letztes Änderungsdatum des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="1ea7d-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="1ea7d-104">In einer gesperrten Active Directory-Umgebung werden authentifizierte Benutzerzugriffs Steuerungs Einträge (ACEs) aus den standardmäßigen Active Directory-Containern, einschließlich der Benutzer, der Konfiguration oder des Systems, und der Organisationseinheiten entfernt, in denen Benutzer und Computer Objekte werden gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1ea7d-104">In a locked-down Active Directory environment, authenticated user access control entries (ACEs) are removed from the default Active Directory containers, including the Users, Configuration or System, and organizational units (OUs) where User and Computer objects are stored.</span></span> <span data-ttu-id="1ea7d-105">Durch das Entfernen von authentifizierten Benutzer-ACEs wird der Lesezugriff auf Active Directory-Informationen verhindert.</span><span class="sxs-lookup"><span data-stu-id="1ea7d-105">Removing authenticated user ACEs prevents read access to Active Directory information.</span></span> <span data-ttu-id="1ea7d-106">Das Entfernen der ACEs führt jedoch zu Problemen bei lync Server 2013, da diese von Leseberechtigungen für diese Container abhängen, damit Benutzer die Domänenvorbereitung ausführen können.</span><span class="sxs-lookup"><span data-stu-id="1ea7d-106">However, removing the ACEs creates issues for Lync Server 2013 because it depends on read permissions to these containers to allow users to run domain preparation.</span></span>

<span data-ttu-id="1ea7d-107">In diesem Fall gewährt die Mitgliedschaft in der Gruppe der Domänenadministratoren, die für die Ausführung der Domänenvorbereitung, Serveraktivierung und Poolerstellung erforderlich ist, keinen Lesezugriff mehr auf Active Directory-Informationen, die in den Standardcontainern gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="1ea7d-107">In this situation, membership in the Domain Admins group, which is required to run domain preparation, server activation, and pool creation, no longer grants read access to Active Directory information stored in the default containers.</span></span> <span data-ttu-id="1ea7d-108">Sie müssen manuell Lesezugriffsberechtigungen für verschiedene Container in der Stammdomäne der Gesamtstruktur erteilen, um zu überprüfen, ob die Vorbereitungs Prozedur für die erforderliche Gesamtstruktur abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="1ea7d-108">You must manually grant read-access permissions on various containers in the forest root domain to check that the prerequisite forest preparation procedure is complete.</span></span>

<span data-ttu-id="1ea7d-109">Damit ein Benutzerdomänen Vorbereitung, Serveraktivierung oder Poolerstellung für eine beliebige Stammdomäne ohne Gesamtstruktur ausführen kann, haben Sie die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="1ea7d-109">To enable a user to run domain preparation, server activation, or pool creation on any non-forest root domain, you have the following options:</span></span>

  - <span data-ttu-id="1ea7d-110">Verwenden Sie ein Konto, das ein Mitglied der Gruppe "Organisations-Admins" ist, um die Domänenvorbereitung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1ea7d-110">Use an account that is a member of the Enterprise Admins group to run domain preparation.</span></span>

  - <span data-ttu-id="1ea7d-111">Verwenden Sie ein Konto, das ein Mitglied der Gruppe der Domänenadministratoren ist, und weisen Sie diesem Konto Lesezugriffsberechtigungen für jeden der folgenden Container in der Gesamtstruktur-Stammdomäne zu:</span><span class="sxs-lookup"><span data-stu-id="1ea7d-111">Use an account that is a member of the Domain Admins group and grant this account read-access permissions on each of the following containers in the forest root domain:</span></span>
    
      - <span data-ttu-id="1ea7d-112">Domäne</span><span class="sxs-lookup"><span data-stu-id="1ea7d-112">Domain</span></span>
    
      - <span data-ttu-id="1ea7d-113">Konfiguration oder System</span><span class="sxs-lookup"><span data-stu-id="1ea7d-113">Configuration or System</span></span>

<span data-ttu-id="1ea7d-114">Wenn Sie kein Konto verwenden möchten, das ein Mitglied der Gruppe "Organisations-Admins" ist, um die Domänenvorbereitung oder andere Setup Aufgaben auszuführen, geben Sie dem Konto, für das Sie Lesezugriff verwenden möchten, explizit die entsprechenden Container im Gesamtstrukturstamm.</span><span class="sxs-lookup"><span data-stu-id="1ea7d-114">If you do not want to use an account that is a member of the Enterprise Admins group to run domain preparation or other Setup tasks, explicitly grant the account you want to use read access on the relevant containers in the forest root.</span></span>

<div>

## <a name="to-give-users-read-access-permissions-on-containers-in-the-forest-root-domain"></a><span data-ttu-id="1ea7d-115">So erteilen Sie Benutzern Lesezugriffsberechtigungen für Container in der Stammdomäne der Gesamtstruktur</span><span class="sxs-lookup"><span data-stu-id="1ea7d-115">To give users read-access permissions on containers in the forest root domain</span></span>

1.  <span data-ttu-id="1ea7d-116">Melden Sie sich bei dem Computer an, der der Gesamtstruktur-Stammdomäne mit einem Konto zugeordnet ist, das ein Mitglied der Gruppe "Domänen-Admins" für die Gesamtstruktur-Stammdomäne ist.</span><span class="sxs-lookup"><span data-stu-id="1ea7d-116">Log on to the computer joined to the forest root domain with an account that is a member of the Domain Admins group for the forest root domain.</span></span>

2.  <span data-ttu-id="1ea7d-117">Führen Sie adsiedit. msc für die Gesamtstruktur-Stammdomäne aus.</span><span class="sxs-lookup"><span data-stu-id="1ea7d-117">Run adsiedit.msc for the forest root domain.</span></span>
    
    <span data-ttu-id="1ea7d-118">Wenn authentifizierte Benutzer-ACEs aus dem Domänen-, Konfigurations-oder System Container entfernt wurden, müssen Sie dem Container schreibgeschützte Berechtigungen erteilen, wie in den folgenden Schritten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1ea7d-118">If authenticated user ACEs were removed from the Domain, Configuration, or System container, you must grant read-only permissions to the container, as described in the following steps.</span></span>

3.  <span data-ttu-id="1ea7d-119">Klicken Sie mit der rechten Maustaste auf den Container, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="1ea7d-119">Right-click the container, and then click **Properties**.</span></span>

4.  <span data-ttu-id="1ea7d-120">Klicken Sie auf die Registerkarte **Sicherheit** .</span><span class="sxs-lookup"><span data-stu-id="1ea7d-120">Click the **Security** tab.</span></span>

5.  <span data-ttu-id="1ea7d-121">Klicken Sie auf **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="1ea7d-121">Click **Advanced**.</span></span>

6.  <span data-ttu-id="1ea7d-122">Klicken Sie auf der Registerkarte **Berechtigungen** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="1ea7d-122">On the **Permissions** tab, click **Add**.</span></span>

7.  <span data-ttu-id="1ea7d-123">Geben Sie den Namen des Benutzers oder der Gruppe ein, der Berechtigungen erhält, indem `domain\account name`Sie folgendes Format verwenden:, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1ea7d-123">Type the name of the user or group receiving permissions by using the following format: `domain\account name`, and then click **OK**.</span></span>

8.  <span data-ttu-id="1ea7d-124">Klicken Sie auf der Registerkarte **Objekte** unter **gilt für**auf **nur dieses Objekt**.</span><span class="sxs-lookup"><span data-stu-id="1ea7d-124">On the **Objects** tab, in **Applies To**, click **This Object Only**.</span></span>

9.  <span data-ttu-id="1ea7d-125">Wählen Sie unter **Berechtigungen**die folgenden ACEs zulassen aus, indem Sie auf die Spalte **zulassen** klicken: **Inhalt**auflisten, **alle Eigenschaften lesen**und **Berechtigungen Lesen**.</span><span class="sxs-lookup"><span data-stu-id="1ea7d-125">In **Permissions**, select the following Allow ACEs by clicking the **Allow** column: **List Content**, **Read All Properties**, and **Read Permissions**.</span></span>

10. <span data-ttu-id="1ea7d-126">Klicken Sie zweimal auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="1ea7d-126">Click **OK** twice.</span></span>

11. <span data-ttu-id="1ea7d-127">Wiederholen Sie diese Schritte für alle relevanten Container, die in Schritt 2 aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="1ea7d-127">Repeat these steps for any of the relevant containers listed in Step 2.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

