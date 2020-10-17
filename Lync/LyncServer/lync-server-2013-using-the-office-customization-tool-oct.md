---
title: 'Lync Server 2013: Verwenden des Office-Anpassungstools (OAT)'
description: 'Lync Server 2013: Verwenden des Office-Anpassungstools (OAT).'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Office Customization Tool (OCT)
ms:assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204748(v=OCS.15)
ms:contentKeyID: 48183654
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 602502ba4579ed6c640eee909d4c6b056ce247d7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547331"
---
# <a name="using-the-office-customization-tool-oct-in-lync-server-2013"></a><span data-ttu-id="dccee-103">Verwenden des Office-Anpassungstools (OAT) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dccee-103">Using the Office Customization Tool (OCT) in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dccee-104">_**Letztes Änderungsstand des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="dccee-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="dccee-105">Das Office-Anpassungstool (OAT) ist Teil des Setup-Programms und ist das empfohlene Tool für viele Anpassungen.</span><span class="sxs-lookup"><span data-stu-id="dccee-105">The Office Customization Tool (OCT) is part of the Setup program and is the recommended tool for many customizations.</span></span> <span data-ttu-id="dccee-106">Mithilfe des OAT passen Sie Office an und speichern Ihre Anpassungen in einer MSP-Setup Anpassungsdatei.</span><span class="sxs-lookup"><span data-stu-id="dccee-106">By using the OCT, you customize Office and save your customizations in a Setup customization .msp file.</span></span> <span data-ttu-id="dccee-107">Legen Sie die Datei am Netzwerkinstallationspfad im Ordner "Updates" ab.</span><span class="sxs-lookup"><span data-stu-id="dccee-107">You place the file in the Updates folder on the network installation point.</span></span> <span data-ttu-id="dccee-108">Bei der Installation von Office sucht das Setupprogramm nach einer Setupanpassungsdatei im Ordner Updates und wendet die Anpassungen an.</span><span class="sxs-lookup"><span data-stu-id="dccee-108">When you install Office, Setup looks for a Setup customization file in the Updates folder and applies the customizations.</span></span> <span data-ttu-id="dccee-109">Der Ordner Updates kann nur zum Bereitstellen von Softwareupdates während einer Erstinstallation von Office 2013 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dccee-109">The Updates folder can be used only to deploy software updates during an initial installation of Office 2013.</span></span>

<span data-ttu-id="dccee-110">Das OAT ist Teil des Setups und ist in Volumenlizenzversionen des Produkts enthalten.</span><span class="sxs-lookup"><span data-stu-id="dccee-110">The OCT is part of setup and it is included in volume license versions of the product.</span></span> <span data-ttu-id="dccee-111">Sie führen das OAT `setup.exe /admin` aus, indem Sie an der Befehlszeile im Stammverzeichnis des Netzwerkinstallationspfads, der die Office 2013 Quelldateien enthält, eingeben.</span><span class="sxs-lookup"><span data-stu-id="dccee-111">You run the OCT by typing `setup.exe /admin` at the command line from the root of the network installation point that contains the Office 2013 source files.</span></span> <span data-ttu-id="dccee-112">Verwenden Sie beispielsweise folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="dccee-112">For example, use the following:</span></span>

`\\server\share\Office15\setup.exe /admin`

<span data-ttu-id="dccee-113">Administratoren verwenden das OAT zum Erstellen einer Setupanpassungsdatei (MSP-Datei).</span><span class="sxs-lookup"><span data-stu-id="dccee-113">Administrators use the OCT to create a setup customization .msp file.</span></span> <span data-ttu-id="dccee-114">Wie im Microsoft Office 2010 OAT können Administratoren die folgenden Bereiche anpassen:</span><span class="sxs-lookup"><span data-stu-id="dccee-114">As in the Microsoft Office 2010 OCT, administrators can customize the following areas:</span></span>

  - <span data-ttu-id="dccee-115">**Setup** Wird verwendet, um den Standard Installationsspeicherort auf dem Client und den Standard Organisationsnamen, zusätzliche Netzwerkinstallationsquellen, Product Key, Endbenutzer-Lizenzvertrag, Anzeigeebene, zu entfernende frühere Office-Versionen, benutzerdefinierte Programme zur Ausführung während der Installation, Sicherheitseinstellungen und Setup Eigenschaften anzugeben.</span><span class="sxs-lookup"><span data-stu-id="dccee-115">**Setup** Used to specify default installation location on the client and default organization name, additional network installation sources, product key, end-user license agreement, display level, earlier versions of Office to remove, custom programs to run during installation, security settings, and Setup properties.</span></span>

  - <span data-ttu-id="dccee-116">**Funktionen** Dient zum Konfigurieren von Benutzereinstellungen und zum Anpassen der Installation von Office-Features.</span><span class="sxs-lookup"><span data-stu-id="dccee-116">**Features** Used to configure user settings and to customize how Office features are installed.</span></span> <span data-ttu-id="dccee-117">Administratoren können das OAT verwenden, um anfängliche Standardwerte für Office-Anwendungseinstellungen für Benutzer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="dccee-117">Administrators can use the OCT to specify initial default values of Office application settings for users.</span></span> <span data-ttu-id="dccee-118">Benutzer können die meisten Einstellungen nach der Installation ändern.</span><span class="sxs-lookup"><span data-stu-id="dccee-118">Users can modify most of the settings after the installation.</span></span>

  - <span data-ttu-id="dccee-119">**Zusätzlicher Inhalt** Wird zum Hinzufügen oder Entfernen von Dateien, zum Hinzufügen oder Entfernen von Registrierungseinträgen und zum Konfigurieren von Verknüpfungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="dccee-119">**Additional content** Used to add or remove files, add or remove registry entries, and configure shortcuts.</span></span>

  - <span data-ttu-id="dccee-120">**Outlook** Dient zum Anpassen des Outlook-Standardprofils eines Benutzers, zum Angeben von Exchange-Einstellungen, zum Hinzufügen von Konten, zum Entfernen von Konten und zum Exportieren von Einstellungen und zum Angeben von Sende \\ Empfangs Gruppen.</span><span class="sxs-lookup"><span data-stu-id="dccee-120">**Outlook** Used to customize a user's default Outlook profile, specify Exchange settings, add accounts, remove accounts and export settings, and specify Send\\Receive groups.</span></span>

<span data-ttu-id="dccee-121">Weitere Informationen zum OAT finden Sie unter <https://go.microsoft.com/fwlink/p/?linkid=267516> .</span><span class="sxs-lookup"><span data-stu-id="dccee-121">For information about the OCT, see <https://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

