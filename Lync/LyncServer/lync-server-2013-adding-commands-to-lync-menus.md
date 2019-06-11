---
title: 'Lync Server 2013: Hinzufügen von Befehlen zu lync-Menüs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Adding commands to Lync menus
ms:assetid: a8443bc2-e234-4022-870a-00700f38b1ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412788(v=OCS.15)
ms:contentKeyID: 48185091
ms.date: 04/11/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1dfb79a985791e6994d8409339d12b12e1146ec5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839936"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-commands-to-lync-menus-in-lync-server-2013"></a><span data-ttu-id="7d09c-102">Hinzufügen von Befehlen zu lync-Menüs in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d09c-102">Adding commands to Lync menus in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d09c-103">_**Letztes Änderungsdatum des Themas:** 2016-04-11_</span><span class="sxs-lookup"><span data-stu-id="7d09c-103">_**Topic Last Modified:** 2016-04-11_</span></span>

<span data-ttu-id="7d09c-104">Sie können den lync 2013-Menüs benutzerdefinierte Befehle hinzufügen und den SIP-URI (Uniform Resource Identifier) des aktuellen Benutzers und ausgewählte Kontakte an die Anwendung übergeben, die der benutzerdefinierte Befehl startet.</span><span class="sxs-lookup"><span data-stu-id="7d09c-104">You can add custom commands to Lync 2013 menus and pass the SIP Uniform Resource Identifier (URI) of the current user and selected contacts to the application that the custom command starts.</span></span>

<span data-ttu-id="7d09c-105">Die benutzerdefinierten Befehle, die Sie hinzufügen, können in einem oder mehreren der folgenden Menüs angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="7d09c-105">The custom commands that you add can appear on one or more of the following menus:</span></span>

  - <span data-ttu-id="7d09c-106">Menü "Extras" auf der Menüleiste im Hauptfenster von lync</span><span class="sxs-lookup"><span data-stu-id="7d09c-106">The Tools menu, on the menu bar in the Lync main window</span></span>

  - <span data-ttu-id="7d09c-107">Das Kontextmenü für Kontakte in der Kontaktliste</span><span class="sxs-lookup"><span data-stu-id="7d09c-107">The shortcut menu for contacts in the Contacts list</span></span>

  - <span data-ttu-id="7d09c-108">Das Menü "Weitere Optionen" im Unterhaltungsfenster</span><span class="sxs-lookup"><span data-stu-id="7d09c-108">The More Options menu, in the Conversation window</span></span>

  - <span data-ttu-id="7d09c-109">Das Kontextmenü für Personen, die in der Teilnehmerliste des Unterhaltungsfensters aufgeführt sind</span><span class="sxs-lookup"><span data-stu-id="7d09c-109">The shortcut menu for people listed in the Conversation window participant list</span></span>

  - <span data-ttu-id="7d09c-110">Menü ' Optionen ' auf einer Visitenkarte</span><span class="sxs-lookup"><span data-stu-id="7d09c-110">The options menu in a contact card</span></span>

<span data-ttu-id="7d09c-111">Sie können benutzerdefinierte Befehle für zwei Arten von Anwendungen definieren – Anwendungen, die eine der folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="7d09c-111">You can define custom commands for two types of applications—applications that do either of the following:</span></span>

  - <span data-ttu-id="7d09c-112">Gelten nur für den aktuellen Benutzer und werden auf dem lokalen Computer gestartet.</span><span class="sxs-lookup"><span data-stu-id="7d09c-112">Apply only to the current user and are started on the local computer.</span></span>

  - <span data-ttu-id="7d09c-113">Beziehen Sie zusätzliche Benutzer ein, beispielsweise ein Online Zusammenarbeitsprogramm, und müssen Sie auf dem Computer jedes Benutzers gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="7d09c-113">Involve additional users, such as an online collaboration program, and must be started on each user's computer.</span></span>

<span data-ttu-id="7d09c-114">Der benutzerdefinierte Befehl kann wie folgt aufgerufen werden:</span><span class="sxs-lookup"><span data-stu-id="7d09c-114">The custom command can be invoked in the following ways:</span></span>

  - <span data-ttu-id="7d09c-115">Wählen Sie einen oder mehrere Benutzer aus, und wählen Sie dann den benutzerdefinierten Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="7d09c-115">Select one or more users, and then choose the custom command.</span></span>

  - <span data-ttu-id="7d09c-116">Starten Sie eine Unterhaltung mit zwei oder mehr Teilnehmern, und wählen Sie dann den benutzerdefinierten Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="7d09c-116">Start a two-party or multiparty conversation, and then choose the custom command.</span></span>

<div>

## <a name="to-add-a-custom-command"></a><span data-ttu-id="7d09c-117">So fügen Sie einen benutzerdefinierten Befehl hinzu</span><span class="sxs-lookup"><span data-stu-id="7d09c-117">To add a custom command</span></span>

<span data-ttu-id="7d09c-118">Verwenden Sie die Registrierungseinstellungen in der folgenden Tabelle, um den Menüs einen Befehl hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="7d09c-118">Use the registry settings in the following table to add a command to the menus.</span></span> <span data-ttu-id="7d09c-119">Diese Einträge werden in der Registrierung an einem der folgenden Speicherorte gespeichert:</span><span class="sxs-lookup"><span data-stu-id="7d09c-119">These entries are placed in the registry at one of the following locations:</span></span>

  - <span data-ttu-id="7d09c-120">Für 32-Bit-\_Betriebs\_System\\:\\HKEY\\-\\Software\\für\\lokale Computer\\Microsoft Office 15,0 lync SessionManager-apps</span><span class="sxs-lookup"><span data-stu-id="7d09c-120">For 32bit OS: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps</span></span>

  - <span data-ttu-id="7d09c-121">Für 64-Bit-\_Betriebs\_System\\:\\HKEY\\local\\Machine\\Software\\Wow6432Node\\Microsoft Office\\15,0 lync SessionManager-apps</span><span class="sxs-lookup"><span data-stu-id="7d09c-121">For 64bit OS: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps</span></span>

### <a name="custom-command-registry-entries"></a><span data-ttu-id="7d09c-122">Registrierungseinträge für benutzerdefinierte Befehle</span><span class="sxs-lookup"><span data-stu-id="7d09c-122">Custom Command Registry Entries</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7d09c-123">Name</span><span class="sxs-lookup"><span data-stu-id="7d09c-123">Name</span></span></th>
<th><span data-ttu-id="7d09c-124">Typ</span><span class="sxs-lookup"><span data-stu-id="7d09c-124">Type</span></span></th>
<th><span data-ttu-id="7d09c-125">Daten</span><span class="sxs-lookup"><span data-stu-id="7d09c-125">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7d09c-126">Name</span><span class="sxs-lookup"><span data-stu-id="7d09c-126">Name</span></span></p></td>
<td><p><span data-ttu-id="7d09c-127">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7d09c-127">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="7d09c-128">Der Name der Anwendung, wie er im Menü angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="7d09c-128">Name of the application as it appears on the menu.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d09c-129">Applicationtype</span><span class="sxs-lookup"><span data-stu-id="7d09c-129">ApplicationType</span></span></p></td>
<td><p><span data-ttu-id="7d09c-130">DWORD</span><span class="sxs-lookup"><span data-stu-id="7d09c-130">DWORD</span></span></p></td>
<td><p><span data-ttu-id="7d09c-131">0 = ausführbare Datei (Standard)</span><span class="sxs-lookup"><span data-stu-id="7d09c-131">0 = Executable (default)</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="7d09c-132">Erfordert ApplicationInstallPath.</span><span class="sxs-lookup"><span data-stu-id="7d09c-132">Requires ApplicationInstallPath.</span></span>


</div>
<p><span data-ttu-id="7d09c-133">1 = Protokoll</span><span class="sxs-lookup"><span data-stu-id="7d09c-133">1 = Protocol</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d09c-134">ApplicationInstallPath</span><span class="sxs-lookup"><span data-stu-id="7d09c-134">ApplicationInstallPath</span></span></p></td>
<td><p><span data-ttu-id="7d09c-135">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7d09c-135">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="7d09c-136">Vollständiger Pfad der ausführbaren Datei.</span><span class="sxs-lookup"><span data-stu-id="7d09c-136">Full path of the executable.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="7d09c-137">Muss angegeben werden, wenn applicationtype 0 (ausführbare Datei) ist.</span><span class="sxs-lookup"><span data-stu-id="7d09c-137">Must be specified if ApplicationType is 0 (Executable).</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d09c-138">Pfad</span><span class="sxs-lookup"><span data-stu-id="7d09c-138">Path</span></span></p></td>
<td><p><span data-ttu-id="7d09c-139">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7d09c-139">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="7d09c-140">Vollständiger Pfad, der zusammen mit allen Parametern gestartet werden soll, einschließlich der Standardparameter <em>% User-ID%</em> und <em>% Contact-ID%</em>.</span><span class="sxs-lookup"><span data-stu-id="7d09c-140">Full path to be started along with any parameters, including the default parameters <em>%user-id%</em> and <em>%contact-id%</em>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d09c-141">SessionType</span><span class="sxs-lookup"><span data-stu-id="7d09c-141">SessionType</span></span></p></td>
<td><p><span data-ttu-id="7d09c-142">DWORD</span><span class="sxs-lookup"><span data-stu-id="7d09c-142">DWORD</span></span></p></td>
<td><p><span data-ttu-id="7d09c-143">0 = lokale Sitzung.</span><span class="sxs-lookup"><span data-stu-id="7d09c-143">0 = Local session.</span></span> <span data-ttu-id="7d09c-144">Die Anwendung wird auf dem lokalen Computer gestartet.</span><span class="sxs-lookup"><span data-stu-id="7d09c-144">The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="7d09c-145">1 = Sitzung mit zwei Teilnehmern (Standard).</span><span class="sxs-lookup"><span data-stu-id="7d09c-145">1 = Two-party session (default).</span></span> <span data-ttu-id="7d09c-146">Lync 2013 startet die Anwendung lokal und sendet dann eine Desktopbenachrichtigung an den anderen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="7d09c-146">Lync 2013 starts the application locally and then sends a desktop notification to the other user.</span></span> <span data-ttu-id="7d09c-147">Der andere Benutzer klickt auf die Benachrichtigung, um die Anwendung auf Ihrem Computer zu starten.</span><span class="sxs-lookup"><span data-stu-id="7d09c-147">The other user clicks the notification to start the application on their computer.</span></span></p>
<p><span data-ttu-id="7d09c-148">2 = mehrteilige Sitzung.</span><span class="sxs-lookup"><span data-stu-id="7d09c-148">2 = Multiparty session.</span></span> <span data-ttu-id="7d09c-149">Lync 2013 startet die Anwendung lokal und sendet dann Desktopbenachrichtigungen an die anderen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="7d09c-149">Lync 2013 starts the application locally and then sends desktop notifications to the other users.</span></span> <span data-ttu-id="7d09c-150">Der andere Benutzer klickt auf die Benachrichtigung, um die angegebene Anwendung auf dem Computer zu starten.</span><span class="sxs-lookup"><span data-stu-id="7d09c-150">The other user clicks the notification to start the specified application on their computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d09c-151">ExtensibleMenu</span><span class="sxs-lookup"><span data-stu-id="7d09c-151">ExtensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="7d09c-152">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7d09c-152">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="7d09c-153">Eine Liste der Menüs, in denen dieser Befehl angezeigt wird, getrennt durch Semikolons.</span><span class="sxs-lookup"><span data-stu-id="7d09c-153">A list of the menus where this command will appear, separated by semicolons.</span></span> <span data-ttu-id="7d09c-154">Mögliche Werte:</span><span class="sxs-lookup"><span data-stu-id="7d09c-154">Possible values are:</span></span></p>
<p><span data-ttu-id="7d09c-155">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="7d09c-155">MainWindowActions</span></span></p>
<p><span data-ttu-id="7d09c-156">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="7d09c-156">MainWindowRightClick</span></span></p>
<p><span data-ttu-id="7d09c-157">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="7d09c-157">ConversationWindowActions</span></span></p>
<p><span data-ttu-id="7d09c-158">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="7d09c-158">ConversationWindowRightClick</span></span></p>
<p><span data-ttu-id="7d09c-159">ContactCardMenu</span><span class="sxs-lookup"><span data-stu-id="7d09c-159">ContactCardMenu</span></span></p>
<p><span data-ttu-id="7d09c-160">Wenn ExtensibleMenu nicht definiert ist, werden die Standardwerte MainWindowRightClick und ConversationWindowActions verwendet.</span><span class="sxs-lookup"><span data-stu-id="7d09c-160">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7d09c-161">Der folgende Registrierungs-Editor (. REG) zeigt die Ergebnisse des Hinzufügens eines Contoso Sales Contact Manager-Menüelements zum Menü "Aktionen" im Unterhaltungsfenster an:</span><span class="sxs-lookup"><span data-stu-id="7d09c-161">For example, the following Registry Editor (.REG) file shows the results of adding a Contoso Sales Contact Manager menu item to Actions menu in the Conversation window:</span></span>

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

## <a name="to-access-a-custom-command"></a><span data-ttu-id="7d09c-162">So greifen Sie auf einen benutzerdefinierten Befehl zu</span><span class="sxs-lookup"><span data-stu-id="7d09c-162">To access a custom command</span></span>

<span data-ttu-id="7d09c-163">Wenn Sie nach dem Hinzufügen auf einen benutzerdefinierten Befehl zugreifen möchten, führen Sie je nach den von Ihnen definierten ExtensibleMenu-Werten eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="7d09c-163">To access a custom command after it is added, do one of the following, depending on the ExtensibleMenu values that you define:</span></span>

  - <span data-ttu-id="7d09c-164">**MainWindowActions**   klicken Sie im Hauptfenster von lync auf **Extras**, und klicken Sie dann auf Ihren benutzerdefinierten Befehl.</span><span class="sxs-lookup"><span data-stu-id="7d09c-164">**MainWindowActions**   In the Lync main window, click **Tools**, and then click your custom command.</span></span>

  - <span data-ttu-id="7d09c-165">**MainWindowRightClick**   klicken Sie im Hauptfenster von lync mit der rechten Maustaste auf einen Kontakt, und klicken Sie dann auf Ihren benutzerdefinierten Befehl.</span><span class="sxs-lookup"><span data-stu-id="7d09c-165">**MainWindowRightClick**   In the Lync main window, right-click a contact, and then click your custom command.</span></span>

  - <span data-ttu-id="7d09c-166">**ConversationWindowActions**   klicken Sie im Unterhaltungsfenster auf das Symbol **Weitere Optionen** , und klicken Sie dann auf Ihren benutzerdefinierten Befehl.</span><span class="sxs-lookup"><span data-stu-id="7d09c-166">**ConversationWindowActions**   In the Conversation window, click the **More Options** icon, and then click your custom command.</span></span>

  - <span data-ttu-id="7d09c-167">**ConversationWindowRightClick**   klicken Sie im Unterhaltungsfenster mit der rechten Maustaste auf einen Kontaktnamen, und klicken Sie dann auf Ihren benutzerdefinierten Befehl.</span><span class="sxs-lookup"><span data-stu-id="7d09c-167">**ConversationWindowRightClick**   In the Conversation window, right-click a contact name, and then click your custom command.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

