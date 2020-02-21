---
title: 'Lync Server 2013: Hinzufügen von Befehlen zu lync-Menüs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding commands to Lync menus
ms:assetid: a8443bc2-e234-4022-870a-00700f38b1ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412788(v=OCS.15)
ms:contentKeyID: 48185091
ms.date: 04/11/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b6377824a7d96e6bb7b0ae6c60c79f3ee4c05b2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203331"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="adding-commands-to-lync-menus-in-lync-server-2013"></a><span data-ttu-id="00044-102">Hinzufügen von Befehlen zu lync-Menüs in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00044-102">Adding commands to Lync menus in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00044-103">_**Letztes Änderungsstand des Themas:** 2016-04-11_</span><span class="sxs-lookup"><span data-stu-id="00044-103">_**Topic Last Modified:** 2016-04-11_</span></span>

<span data-ttu-id="00044-104">Sie können benutzerdefinierte Befehle zu lync 2013 Menüs hinzufügen und den SIP-URI (Uniform Resource Identifier) des aktuellen Benutzers und der ausgewählten Kontakte an die Anwendung übergeben, die mit dem benutzerdefinierten Befehl gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="00044-104">You can add custom commands to Lync 2013 menus and pass the SIP Uniform Resource Identifier (URI) of the current user and selected contacts to the application that the custom command starts.</span></span>

<span data-ttu-id="00044-105">Die benutzerdefinierten Befehle, die Sie hinzufügen, können in einem oder mehreren der folgenden Menüs angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="00044-105">The custom commands that you add can appear on one or more of the following menus:</span></span>

  - <span data-ttu-id="00044-106">Das Menü "Extras" auf der Menüleiste im lync-Hauptfenster</span><span class="sxs-lookup"><span data-stu-id="00044-106">The Tools menu, on the menu bar in the Lync main window</span></span>

  - <span data-ttu-id="00044-107">Das Kontextmenü für Kontakte in der Kontaktliste</span><span class="sxs-lookup"><span data-stu-id="00044-107">The shortcut menu for contacts in the Contacts list</span></span>

  - <span data-ttu-id="00044-108">Im Menü "Weitere Optionen" im Fenster "Unterhaltung"</span><span class="sxs-lookup"><span data-stu-id="00044-108">The More Options menu, in the Conversation window</span></span>

  - <span data-ttu-id="00044-109">Das Kontextmenü für Personen, die in der Teilnehmerliste des Unterhaltungsfensters aufgeführt sind</span><span class="sxs-lookup"><span data-stu-id="00044-109">The shortcut menu for people listed in the Conversation window participant list</span></span>

  - <span data-ttu-id="00044-110">Das Menü "Optionen" auf einer Visitenkarte</span><span class="sxs-lookup"><span data-stu-id="00044-110">The options menu in a contact card</span></span>

<span data-ttu-id="00044-111">Sie können benutzerdefinierte Befehle für zwei Anwendungstypen definieren – Anwendungen, die eine der folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="00044-111">You can define custom commands for two types of applications—applications that do either of the following:</span></span>

  - <span data-ttu-id="00044-112">Gilt nur für den aktuellen Benutzer und wird auf dem lokalen Computer gestartet.</span><span class="sxs-lookup"><span data-stu-id="00044-112">Apply only to the current user and are started on the local computer.</span></span>

  - <span data-ttu-id="00044-113">Beziehen Sie zusätzliche Benutzer ein, beispielsweise ein Online-Zusammenarbeitsprogramm, und müssen Sie auf den Computern der einzelnen Benutzer gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="00044-113">Involve additional users, such as an online collaboration program, and must be started on each user's computer.</span></span>

<span data-ttu-id="00044-114">Der benutzerdefinierte Befehl kann auf folgende Weise aufgerufen werden:</span><span class="sxs-lookup"><span data-stu-id="00044-114">The custom command can be invoked in the following ways:</span></span>

  - <span data-ttu-id="00044-115">Wählen Sie einen oder mehrere Benutzer aus, und wählen Sie dann den benutzerdefinierten Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="00044-115">Select one or more users, and then choose the custom command.</span></span>

  - <span data-ttu-id="00044-116">Starten Sie eine Unterhaltung mit zwei oder mehr Teilnehmern, und wählen Sie dann den benutzerdefinierten Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="00044-116">Start a two-party or multiparty conversation, and then choose the custom command.</span></span>

<div>

## <a name="to-add-a-custom-command"></a><span data-ttu-id="00044-117">So fügen Sie einen benutzerdefinierten Befehl hinzu</span><span class="sxs-lookup"><span data-stu-id="00044-117">To add a custom command</span></span>

<span data-ttu-id="00044-118">Verwenden Sie die Registrierungseinstellungen in der folgenden Tabelle, um den Menüs einen Befehl hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="00044-118">Use the registry settings in the following table to add a command to the menus.</span></span> <span data-ttu-id="00044-119">Diese Einträge werden an einem der folgenden Speicherorte in der Registrierung gespeichert:</span><span class="sxs-lookup"><span data-stu-id="00044-119">These entries are placed in the registry at one of the following locations:</span></span>

  - <span data-ttu-id="00044-120">Für 32bit OS: HKEY\_local\_Machine\\Software\\Microsoft\\Office\\15,0\\lync\\SessionManager\\apps</span><span class="sxs-lookup"><span data-stu-id="00044-120">For 32bit OS: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps</span></span>

  - <span data-ttu-id="00044-121">Für 64bit OS: HKEY\_local\_Machine\\Software\\Wow6432Node\\Microsoft\\Office\\15,0\\lync\\SessionManager\\apps</span><span class="sxs-lookup"><span data-stu-id="00044-121">For 64bit OS: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps</span></span>

### <a name="custom-command-registry-entries"></a><span data-ttu-id="00044-122">Registrierungseinträge für benutzerdefinierte Befehle</span><span class="sxs-lookup"><span data-stu-id="00044-122">Custom Command Registry Entries</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="00044-123">Name</span><span class="sxs-lookup"><span data-stu-id="00044-123">Name</span></span></th>
<th><span data-ttu-id="00044-124">Typ</span><span class="sxs-lookup"><span data-stu-id="00044-124">Type</span></span></th>
<th><span data-ttu-id="00044-125">Daten</span><span class="sxs-lookup"><span data-stu-id="00044-125">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00044-126">Name</span><span class="sxs-lookup"><span data-stu-id="00044-126">Name</span></span></p></td>
<td><p><span data-ttu-id="00044-127">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="00044-127">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="00044-128">Name der Anwendung, wie er im Menü angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="00044-128">Name of the application as it appears on the menu.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00044-129">ApplicationType</span><span class="sxs-lookup"><span data-stu-id="00044-129">ApplicationType</span></span></p></td>
<td><p><span data-ttu-id="00044-130">DWORD</span><span class="sxs-lookup"><span data-stu-id="00044-130">DWORD</span></span></p></td>
<td><p><span data-ttu-id="00044-131">0 = ausführbar (Standard)</span><span class="sxs-lookup"><span data-stu-id="00044-131">0 = Executable (default)</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="00044-132">Erfordert ApplicationInstallPath.</span><span class="sxs-lookup"><span data-stu-id="00044-132">Requires ApplicationInstallPath.</span></span>


</div>
<p><span data-ttu-id="00044-133">1 = Protokoll</span><span class="sxs-lookup"><span data-stu-id="00044-133">1 = Protocol</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00044-134">ApplicationInstallPath</span><span class="sxs-lookup"><span data-stu-id="00044-134">ApplicationInstallPath</span></span></p></td>
<td><p><span data-ttu-id="00044-135">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="00044-135">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="00044-136">Vollständiger Pfad der ausführbaren Datei.</span><span class="sxs-lookup"><span data-stu-id="00044-136">Full path of the executable.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="00044-137">Muss angegeben werden, wenn applicationtype auf 0 (ausführbar) festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="00044-137">Must be specified if ApplicationType is 0 (Executable).</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00044-138">Pfad</span><span class="sxs-lookup"><span data-stu-id="00044-138">Path</span></span></p></td>
<td><p><span data-ttu-id="00044-139">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="00044-139">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="00044-140">Vollständiger Pfad, der zusammen mit allen Parametern gestartet werden soll, einschließlich der Standardparameter <em>% User-ID%</em> und <em>% Contact-ID%</em>.</span><span class="sxs-lookup"><span data-stu-id="00044-140">Full path to be started along with any parameters, including the default parameters <em>%user-id%</em> and <em>%contact-id%</em>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00044-141">SessionType</span><span class="sxs-lookup"><span data-stu-id="00044-141">SessionType</span></span></p></td>
<td><p><span data-ttu-id="00044-142">DWORD</span><span class="sxs-lookup"><span data-stu-id="00044-142">DWORD</span></span></p></td>
<td><p><span data-ttu-id="00044-p102">0 = Lokale Sitzung. Die Anwendung wird auf dem lokalen Computer gestartet.</span><span class="sxs-lookup"><span data-stu-id="00044-p102">0 = Local session. The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="00044-145">1 = Sitzung mit zwei Teilnehmern (Standardeinstellung).</span><span class="sxs-lookup"><span data-stu-id="00044-145">1 = Two-party session (default).</span></span> <span data-ttu-id="00044-146">Lync 2013 startet die Anwendung lokal und sendet dann eine Desktopbenachrichtigung an den anderen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="00044-146">Lync 2013 starts the application locally and then sends a desktop notification to the other user.</span></span> <span data-ttu-id="00044-147">Der andere Benutzer klickt auf die Benachrichtigung, um die Anwendung auf Ihrem Computer zu starten.</span><span class="sxs-lookup"><span data-stu-id="00044-147">The other user clicks the notification to start the application on their computer.</span></span></p>
<p><span data-ttu-id="00044-148">2 = mehrteilige Sitzung.</span><span class="sxs-lookup"><span data-stu-id="00044-148">2 = Multiparty session.</span></span> <span data-ttu-id="00044-149">Lync 2013 startet die Anwendung lokal und sendet anschließend Desktopbenachrichtigungen an die anderen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="00044-149">Lync 2013 starts the application locally and then sends desktop notifications to the other users.</span></span> <span data-ttu-id="00044-150">Der andere Benutzer klickt auf die Benachrichtigung, um die angegebene Anwendung auf Ihrem Computer zu starten.</span><span class="sxs-lookup"><span data-stu-id="00044-150">The other user clicks the notification to start the specified application on their computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00044-151">ExtensibleMenu</span><span class="sxs-lookup"><span data-stu-id="00044-151">ExtensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="00044-152">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="00044-152">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="00044-153">Eine Liste der Menüs, in denen dieser Befehl durch Semikolons getrennt angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="00044-153">A list of the menus where this command will appear, separated by semicolons.</span></span> <span data-ttu-id="00044-154">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="00044-154">Possible values are:</span></span></p>
<p><span data-ttu-id="00044-155">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="00044-155">MainWindowActions</span></span></p>
<p><span data-ttu-id="00044-156">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="00044-156">MainWindowRightClick</span></span></p>
<p><span data-ttu-id="00044-157">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="00044-157">ConversationWindowActions</span></span></p>
<p><span data-ttu-id="00044-158">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="00044-158">ConversationWindowRightClick</span></span></p>
<p><span data-ttu-id="00044-159">ContactCardMenu</span><span class="sxs-lookup"><span data-stu-id="00044-159">ContactCardMenu</span></span></p>
<p><span data-ttu-id="00044-160">Wenn "ExtensibleMenu" nicht definiert ist, werden die Standardwerte von "MainWindowRightClick" und "ConversationWindowActions" verwendet.</span><span class="sxs-lookup"><span data-stu-id="00044-160">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="00044-161">Beispielsweise wird der folgende Registrierungs-Editor (. REG) zeigt die Ergebnisse des Hinzufügens eines Contoso-Menüelements "Sales Contact Manager" im Menü "Aktionen" im Fenster "Unterhaltung" an:</span><span class="sxs-lookup"><span data-stu-id="00044-161">For example, the following Registry Editor (.REG) file shows the results of adding a Contoso Sales Contact Manager menu item to Actions menu in the Conversation window:</span></span>

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Office\15.0\Lync\SessionManager\Apps\{1F9F07C6-7E0B-462B-AAD7-98C6DBEA8F69}]
    "Name"="Contoso Sales Contact Manager"
    "HelpMessage"="The Contoso Sales Contact Manager is not installed. Contact the Help Desk for more information."
    "ApplicationType"=dword:00000000
    "ApplicationInstallPath"="C:\\cscm.exe"
    "Path"="C:\\cscm.exe %user-id% %contact-id%"
    "SessionType"=dword:00000001
    "ExtensibleMenu"="ConversationWindowActions;MainWindowRightClick"

</div>

<div>

## <a name="to-access-a-custom-command"></a><span data-ttu-id="00044-162">So greifen Sie auf einen benutzerdefinierten Befehl zu</span><span class="sxs-lookup"><span data-stu-id="00044-162">To access a custom command</span></span>

<span data-ttu-id="00044-163">Wenn Sie nach dem Hinzufügen auf einen benutzerdefinierten Befehl zugreifen möchten, führen Sie je nach den von Ihnen definierten ExtensibleMenu-Werten einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="00044-163">To access a custom command after it is added, do one of the following, depending on the ExtensibleMenu values that you define:</span></span>

  - <span data-ttu-id="00044-164">**MainWindowActions**   klicken Sie im lync-Hauptfenster auf **Extras**, und klicken Sie dann auf Ihren benutzerdefinierten Befehl.</span><span class="sxs-lookup"><span data-stu-id="00044-164">**MainWindowActions**   In the Lync main window, click **Tools**, and then click your custom command.</span></span>

  - <span data-ttu-id="00044-165">**MainWindowRightClick**   klicken Sie im lync-Hauptfenster mit der rechten Maustaste auf einen Kontakt, und klicken Sie dann auf Ihren benutzerdefinierten Befehl.</span><span class="sxs-lookup"><span data-stu-id="00044-165">**MainWindowRightClick**   In the Lync main window, right-click a contact, and then click your custom command.</span></span>

  - <span data-ttu-id="00044-166">**ConversationWindowActions**   klicken Sie im Fenster Unterhaltung auf das Symbol **Weitere Optionen** , und klicken Sie dann auf Ihren benutzerdefinierten Befehl.</span><span class="sxs-lookup"><span data-stu-id="00044-166">**ConversationWindowActions**   In the Conversation window, click the **More Options** icon, and then click your custom command.</span></span>

  - <span data-ttu-id="00044-167">**ConversationWindowRightClick**   klicken Sie im Fenster Unterhaltung mit der rechten Maustaste auf einen Kontaktnamen, und klicken Sie dann auf Ihren benutzerdefinierten Befehl.</span><span class="sxs-lookup"><span data-stu-id="00044-167">**ConversationWindowRightClick**   In the Conversation window, right-click a contact name, and then click your custom command.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

