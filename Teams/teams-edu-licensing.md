---
title: Microsoft Teams-Ressourcen für Administratoren in Bildungseinrichtungen
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Exemplarische Vorgehensweise für die Lizenzierung von Microsoft Teams für Bildungseinrichtungen.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
appliesto:
- Microsoft Teams
ms.openlocfilehash: b7d5ebd0552aafffe2eb2330e6945f99dd788b2f
ms.sourcegitcommit: 86366b66b15870fe83cbb76e1ae7aa1ce9b3bfe1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2020
ms.locfileid: "42858630"
---
# <a name="assign-microsoft-teams-licenses-for-edu"></a><span data-ttu-id="083b1-103">Zuweisen von Microsoft Teams-Lizenzen für Bildungseinrichtungen</span><span class="sxs-lookup"><span data-stu-id="083b1-103">Assign Microsoft Teams licenses for EDU</span></span>

<span data-ttu-id="083b1-104">Microsoft Teams ist ein digitaler Hub, der Unterhaltungen, Inhalte und Apps an einem zentralen Ort zusammenbringt.</span><span class="sxs-lookup"><span data-stu-id="083b1-104">Microsoft Teams is a digital hub that brings conversations, content, and apps together in one place.</span></span> <span data-ttu-id="083b1-105">Da es auf Office 365 basiert, profitieren Bildungseinrichtungen von der Integration in die vertrauten Office-Apps und -Dienste.</span><span class="sxs-lookup"><span data-stu-id="083b1-105">Because it's built on Office 365, schools benefit from integration with their familiar Office apps and services.</span></span> <span data-ttu-id="083b1-106">Mit Microsoft Teams kann Ihre Institution gemeinsame Kursräume erstellen, sich in professionellen Lerngemeinschaften (Professional Learning Communities, PLCs) verbinden und mit den Mitarbeitern ihrer Bildungseinrichtung kommunizieren – alles das über eine einzige Benutzeroberfläche in Office 365 Education.</span><span class="sxs-lookup"><span data-stu-id="083b1-106">Your institution can use Microsoft Teams to create collaborative classrooms, connect in professional learning communities, and communicate with school staff all from a single experience in Office 365 for Education.</span></span>

<span data-ttu-id="083b1-107">Zum Einstieg müssen IT-Administratoren das Microsoft 365 Admin Center verwenden, um [Microsoft Teams für ihre Bildungseinrichtung zu aktivieren](https://docs.microsoft.com/microsoft-365/education/intune-edu-trial/enable-microsoft-teams).</span><span class="sxs-lookup"><span data-stu-id="083b1-107">To get started, IT administrators need to use the Microsoft 365 Admin Center to [enable Microsoft Teams for your school](https://docs.microsoft.com/microsoft-365/education/intune-edu-trial/enable-microsoft-teams).</span></span>
<span data-ttu-id="083b1-108">Anschließend müssen Sie den Benutzerkonten Lizenzen zuweisen, damit ihre Lehrkräfte, Mitarbeiter und Schüler/Studenten auf Office 365-Dienste wie Microsoft Teams zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="083b1-108">Once complete, you must assign licenses to user accounts so your faculty, staff, and students can access Office 365 services, such as Microsoft Teams.</span></span>

<span data-ttu-id="083b1-109">Sie können Benutzerkonten Lizenzen entweder einzeln oder automatisch über eine Gruppenmitgliedschaft zuweisen.</span><span class="sxs-lookup"><span data-stu-id="083b1-109">You can assign licenses to user accounts either individually or automatically through group membership.</span></span> <span data-ttu-id="083b1-110">In diesem Artikel erfahren Sie, wie Sie einem einzelnen Benutzer oder einer kleinen Gruppe von Benutzerkonten über das Microsoft 365 Admin Center Office 365-Lizenzen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="083b1-110">This article will walk you through how to assign Office 365 licenses to an individual or a small set of user accounts via the Microsoft 365 admin center.</span></span> <span data-ttu-id="083b1-111">Informationen zum automatischen Zuweisen von Lizenzen über eine Gruppenmitgliedschaft finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="083b1-111">To assign licenses automatically through group membership, see one of our supporting articles:</span></span>

- [<span data-ttu-id="083b1-112">Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="083b1-112">Office 365 Powershell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)
- [<span data-ttu-id="083b1-113">Gruppenbasierte Lizenzierung in Active Directory</span><span class="sxs-lookup"><span data-stu-id="083b1-113">Group-based Licensing in Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)

<span data-ttu-id="083b1-114">Sie können Benutzern entweder auf der Seite **Lizenzen** oder auf der Seite **Aktive Benutzer** Lizenzen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="083b1-114">You can assign licenses to users on either the **Licenses** page, or on the **Active Users** page.</span></span> <span data-ttu-id="083b1-115">Welche Methode Sie verwenden, hängt davon ab, ob Sie bestimmten Benutzern Produktlizenzen zuweisen oder Benutzern Lizenzen für bestimmte Produkte zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="083b1-115">Which method you use depends on whether you want to assign product licenses to specific users, or assign users licenses to specific products.</span></span>

> [!NOTE]
> <span data-ttu-id="083b1-116">Wenn Sie das neue Microsoft 365 Admin Center nicht verwenden, können Sie es aktivieren, indem Sie den Umschalter **Das neue Admin Center** am oberen Rand der Startseite auswählen.</span><span class="sxs-lookup"><span data-stu-id="083b1-116">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

## <a name="assign-licenses-to-users-on-the-licenses-page"></a><span data-ttu-id="083b1-117">Benutzern auf der Seite "Lizenzen" Lizenzen zuweisen</span><span class="sxs-lookup"><span data-stu-id="083b1-117">Assign licenses to users on the Licenses page</span></span>

> [!NOTE]
> <span data-ttu-id="083b1-118">Sie müssen globaler Administrator, Abrechnungsadministrator, Lizenzadministrator oder Benutzerverwaltungsadministrator sein. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen von Office 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="083b1-118">You must be a Global admin, Billing admin, License admin, or User management admin. For more information, see [About Office 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="083b1-119">Wenn Sie zum Zuweisen von Lizenzen die Seite **Lizenzen** verwenden, können Sie bis zu 20 Benutzern Lizenzen für ein bestimmtes Produkt zuweisen.</span><span class="sxs-lookup"><span data-stu-id="083b1-119">When you use the **Licenses** page to assign licenses, you assign licenses for a specific product for up to 20 users.</span></span> <span data-ttu-id="083b1-120">Auf der Seite **Lizenzen** wird eine Liste aller Produkte angezeigt, für die Sie über Abonnements verfügen. Außerdem sehen Sie hier die Gesamtzahl der Lizenzen für jedes Produkt und erfahren, wie viele Lizenzen zugewiesen und wie viele verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="083b1-120">On the **Licenses** page, you see a list of all the products you have subscriptions for, together with the total number of licenses for each product, how many licenses are assigned, and how many are available.</span></span>

1. <span data-ttu-id="083b1-121">Navigieren Sie im Admin Center zur Seite **Abrechnung** > [Lizenzen](https://go.microsoft.com/fwlink/p/?linkid=842264).</span><span class="sxs-lookup"><span data-stu-id="083b1-121">In the admin center, go to the **Billing** > [Licenses](https://go.microsoft.com/fwlink/p/?linkid=842264) page.</span></span>

   ![Screenshot des Abrechnungsfensters und der Menüoptionen.](media/EDU-Lic-Billing-License.png)
2. <span data-ttu-id="083b1-123">Wählen Sie ein Produkt aus, für das Sie Lizenzen zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="083b1-123">Select a product for which you want to assign licenses.</span></span> <span data-ttu-id="083b1-124">Microsoft Teams ist ein Bestandteil der kostenlosen Office 365 A1 für Schüler und Studenten-SKU.</span><span class="sxs-lookup"><span data-stu-id="083b1-124">Microsoft Teams is part of the free Office 365 A1 for Students SKU.</span></span>

   ![Screenshot der Seite "Lizenzen" mit verfügbaren Produkten, deren Lizenzen Sie zuweisen können.](media/EDU-Lic-Licenses-Products.png)
3. <span data-ttu-id="083b1-126">Wählen Sie **Lizenzen zuweisen** aus.</span><span class="sxs-lookup"><span data-stu-id="083b1-126">Select **Assign licenses**.</span></span>

   ![Screenshot des Abschnitts "Benutzer" der Seite und der Option "Lizenzen zuweisen" mit einem Pluszeichen davor.](media/EDU-Lic-Assign-Licenses.png)
4. <span data-ttu-id="083b1-128">Beginnen Sie im Bereich **Benutzern Lizenzen zuweisen** mit der Eingabe eines Namens, um eine Liste von Namen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="083b1-128">In the **Assign licenses to users** pane, begin typing a name, which should generate a list of names.</span></span> <span data-ttu-id="083b1-129">Wählen Sie den gewünschten Namen aus den Ergebnissen aus, um ihn der Liste hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="083b1-129">Choose the name you're looking for from the results to add it to the list.</span></span> <span data-ttu-id="083b1-130">Sie können bis zu 20 Benutzer gleichzeitig hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="083b1-130">You can add up to 20 users at a time.</span></span>

   ![Screenshot der Seite "Benutzern Lizenzen zuweisen" mit einem teilweise eingegebenen Namen und den eingeblendeten Suchergebnissen für diesen Teilnamen.](media/EDU-Lic-Assign-Licenses-Users.png)
5. <span data-ttu-id="083b1-132">Wählen Sie **Apps und Dienste aktivieren oder deaktivieren** aus, um den Zugriff auf bestimmte Elemente, z. B. Microsoft Teams, zuzuweisen oder zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="083b1-132">Select **Turn apps and services on or off** to assign or remove access to specific items, such as Microsoft Teams.</span></span> <span data-ttu-id="083b1-133">Stellen Sie sicher, dass **Microsoft Teams** und **Office für das Web (Education)** ausgewählt sind.</span><span class="sxs-lookup"><span data-stu-id="083b1-133">Ensure **Microsoft Teams** and **Office for the web (Education)** are selected.</span></span>
6. <span data-ttu-id="083b1-134">Wählen Sie abschließend **Zuweisen** und dann **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="083b1-134">When you're finished, select **Assign**, then select **Close**.</span></span>

<span data-ttu-id="083b1-135">So ändern Sie die Apps und Dienste, auf die ein Benutzer zugreifen kann</span><span class="sxs-lookup"><span data-stu-id="083b1-135">To change the apps and services a user has access to:</span></span>

1. <span data-ttu-id="083b1-136">Wählen Sie die Zeile aus, die den Benutzer enthält.</span><span class="sxs-lookup"><span data-stu-id="083b1-136">Select the row that contains the user.</span></span>
1. <span data-ttu-id="083b1-137">Aktivieren bzw. deaktivieren Sie im rechten Bereich die Apps und Dienste, für die Sie Zugriff gewähren oder entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="083b1-137">In the right pane, select or deselect the apps and services that you want to give access to, or remove access from.</span></span>
1. <span data-ttu-id="083b1-138">Wählen Sie abschließend **Speichern** und dann **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="083b1-138">When you're finished, select **Save**, then select **Close**.</span></span>

## <a name="assign-licenses-to-an-individual-or-multiple-users-on-the-active-users-page"></a><span data-ttu-id="083b1-139">Zuweisen von Lizenzen zu einem oder mehreren Benutzern auf der Seite "Aktive Benutzer"</span><span class="sxs-lookup"><span data-stu-id="083b1-139">Assign licenses to an individual or multiple users on the Active users page</span></span>

1. <span data-ttu-id="083b1-140">Wechseln Sie im Admin Center zu der Seite **Benutzer** > [Aktive Benutzer](https://go.microsoft.com/fwlink/p/?linkid=834822).</span><span class="sxs-lookup"><span data-stu-id="083b1-140">In the admin center, go to the **Users** > [Active users](https://go.microsoft.com/fwlink/p/?linkid=834822) page.</span></span>

   ![Screenshot der Menüoption "aktive Benutzer" im Microsoft O365 Admin Center.](media/EDU-Lic-Active-Users.png)
2. <span data-ttu-id="083b1-142">Aktivieren Sie die Kreise neben den Namen der Benutzer, denen Sie Lizenzen zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="083b1-142">Select the circles next to the name(s) of the user(s) you want to assign license(s) to.</span></span>

   ![Screenshot der Seite "Aktive Benutzer" und einer Liste der aktiven Benutzer auf dieser Seite, wobei einige Benutzer ausgewählt sind (der Kreis neben ihren Namen ist ausgefüllt).](media/EDU-Lic-Active-Users-List.png)
3. <span data-ttu-id="083b1-144">Wählen Sie am oberen Rand **Produktlizenzen verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="083b1-144">At the top select **Manage product licenses**.</span></span>

   ![Screenshot der Registerkarte "Produktlizenzen verwalten", darunter ein Benutzer, der als "nicht lizenziert" angegeben ist.](media/EDU-Lic-Manage-Product-Licenses.png)
4. <span data-ttu-id="083b1-146">Wählen Sie im Bereich **Produktlizenzen verwalten** die Optionen **Zu vorhandenen Produktlizenzzuweisungen hinzufügen** > **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="083b1-146">In the **Manage product licenses** pane, select **Add to existing product license assignments** > **Next**.</span></span>

   ![Screenshot des Fensters "Produktlizenzen verwalten" mit ausgewähltem Optionsfeld "Zu vorhandenen Produktlizenzzuweisungen hinzufügen".](media/EDU-Lic-Add-Existing-Product.png)
5. <span data-ttu-id="083b1-148">Setzen Sie im Bereich **Zu vorhandenen Produktlizenzzuweisungen hinzufügen** die Umschaltfläche für die Lizenz, die der ausgewählten Benutzer erhalten soll, auf die Stellung **Ein**.</span><span class="sxs-lookup"><span data-stu-id="083b1-148">In the **Add to existing products** pane, switch the toggle to the **On** position for the license that you want the selected users to have.</span></span> <span data-ttu-id="083b1-149">Stellen Sie sicher, dass **Microsoft Teams** und **Office für das Web (Education)** ausgewählt sind.</span><span class="sxs-lookup"><span data-stu-id="083b1-149">Ensure **Microsoft Teams** and **Office for the web (Education)** are selected.</span></span>

   ![Screenshot von Microsoft Teams und Office für das Web (Education), ausgewählt auf der Registerkarte "Zu vorhandenen Produkten hinzufügen".](media/EDU-Lic-Add-Existing-Products.png)

   <span data-ttu-id="083b1-151">Standardmäßig werden alle diesen Lizenzen zugeordneten Dienste dem Benutzer automatisch zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="083b1-151">By default, all services associated with those license(s) are automatically assigned to the user(s).</span></span> <span data-ttu-id="083b1-152">Sie können die für die Benutzer verfügbaren Dienste einschränken.</span><span class="sxs-lookup"><span data-stu-id="083b1-152">You can limit which services are available to the users.</span></span> <span data-ttu-id="083b1-153">Setzen Sie die Umschaltfläche für die Dienste, die die Benutzer nicht erhalten sollen, auf die Stellung **Aus**.</span><span class="sxs-lookup"><span data-stu-id="083b1-153">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="083b1-154">Wählen Sie am unteren Rand des Bereichs "Hinzufügen" > "Schließen" aus.</span><span class="sxs-lookup"><span data-stu-id="083b1-154">At the bottom of the pane, select Add > Close.</span></span>
