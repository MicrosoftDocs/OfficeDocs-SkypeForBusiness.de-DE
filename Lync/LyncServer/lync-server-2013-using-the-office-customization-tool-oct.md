---
title: 'Lync Server 2013: Verwenden des Office-Anpassungstools (OAT)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using the Office Customization Tool (OCT)
ms:assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204748(v=OCS.15)
ms:contentKeyID: 48183654
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cbdd9c101b9098f9a5a6ac6088740c067039921b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847304"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-office-customization-tool-oct-in-lync-server-2013"></a><span data-ttu-id="ae306-102">Verwenden des Office-Anpassungstools (OAT) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae306-102">Using the Office Customization Tool (OCT) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae306-103">_**Letztes Änderungsdatum des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="ae306-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="ae306-104">Das Office-Anpassungstool (OAT) ist Teil des Setup-Programms und wird als Tool für viele Anpassungen empfohlen.</span><span class="sxs-lookup"><span data-stu-id="ae306-104">The Office Customization Tool (OCT) is part of the Setup program and is the recommended tool for many customizations.</span></span> <span data-ttu-id="ae306-105">Wenn Sie das OAT verwenden, passen Sie Office an, und speichern Sie Ihre Anpassungen in einer MSP-Datei für die Setup Anpassung.</span><span class="sxs-lookup"><span data-stu-id="ae306-105">By using the OCT, you customize Office and save your customizations in a Setup customization .msp file.</span></span> <span data-ttu-id="ae306-106">Sie fügen die Datei im Ordner Updates auf dem Netzwerkinstallationspfad ein.</span><span class="sxs-lookup"><span data-stu-id="ae306-106">You place the file in the Updates folder on the network installation point.</span></span> <span data-ttu-id="ae306-107">Wenn Sie Office installieren, sucht Setup im Ordner Updates nach einer Setupanpassungsdatei und wendet die Anpassungen an.</span><span class="sxs-lookup"><span data-stu-id="ae306-107">When you install Office, Setup looks for a Setup customization file in the Updates folder and applies the customizations.</span></span> <span data-ttu-id="ae306-108">Der Ordner Updates kann nur zum Bereitstellen von Softwareupdates während einer Erstinstallation von Office 2013 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ae306-108">The Updates folder can be used only to deploy software updates during an initial installation of Office 2013.</span></span>

<span data-ttu-id="ae306-109">Das OAT ist Teil des Setups und in Volumenlizenzversionen des Produkts enthalten.</span><span class="sxs-lookup"><span data-stu-id="ae306-109">The OCT is part of setup and it is included in volume license versions of the product.</span></span> <span data-ttu-id="ae306-110">Sie führen das OAT durch Eingabe `setup.exe /admin` über die Befehlszeile aus dem Stammverzeichnis des Netzwerkinstallationspfads, der die Office 2013-Quelldateien enthält.</span><span class="sxs-lookup"><span data-stu-id="ae306-110">You run the OCT by typing `setup.exe /admin` at the command line from the root of the network installation point that contains the Office 2013 source files.</span></span> <span data-ttu-id="ae306-111">Verwenden Sie beispielsweise folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="ae306-111">For example, use the following:</span></span>

`\\server\share\Office15\setup.exe /admin`

<span data-ttu-id="ae306-112">Administratoren verwenden das OAT zum Erstellen einer Setupanpassungsdatei (MSP-Datei).</span><span class="sxs-lookup"><span data-stu-id="ae306-112">Administrators use the OCT to create a setup customization .msp file.</span></span> <span data-ttu-id="ae306-113">Wie im Microsoft Office 2010 Oct können Administratoren die folgenden Bereiche anpassen:</span><span class="sxs-lookup"><span data-stu-id="ae306-113">As in the Microsoft Office 2010 OCT, administrators can customize the following areas:</span></span>

  - <span data-ttu-id="ae306-114">**Einrichtung** Dient zum Angeben des Standard Installationsspeicherorts auf dem Client und dem Standard Organisationsnamen, zusätzliche Netzwerkinstallationsquellen, Product Key, Endbenutzer-Lizenzvertrag, Anzeigeebene, zu entfernende frühere Office-Versionen, benutzerdefinierte Programme, die ausgeführt werden sollen. Installations-, Sicherheitseinstellungen und Setup Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="ae306-114">**Setup** Used to specify default installation location on the client and default organization name, additional network installation sources, product key, end-user license agreement, display level, earlier versions of Office to remove, custom programs to run during installation, security settings, and Setup properties.</span></span>

  - <span data-ttu-id="ae306-115">**Funktionen** Wird verwendet, um Benutzereinstellungen zu konfigurieren und die Installation von Office-Features anzupassen.</span><span class="sxs-lookup"><span data-stu-id="ae306-115">**Features** Used to configure user settings and to customize how Office features are installed.</span></span> <span data-ttu-id="ae306-116">Administratoren können das OAT verwenden, um anfängliche Standardwerte für die Office-Anwendungseinstellungen für Benutzer festzulegen.</span><span class="sxs-lookup"><span data-stu-id="ae306-116">Administrators can use the OCT to specify initial default values of Office application settings for users.</span></span> <span data-ttu-id="ae306-117">Benutzer können die meisten Einstellungen nach der Installation ändern.</span><span class="sxs-lookup"><span data-stu-id="ae306-117">Users can modify most of the settings after the installation.</span></span>

  - <span data-ttu-id="ae306-118">**Zusätzlicher Inhalt** Wird zum Hinzufügen oder Entfernen von Dateien, hinzufügen oder Entfernen von Registrierungseinträgen und Konfigurieren von Tastenkombinationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="ae306-118">**Additional content** Used to add or remove files, add or remove registry entries, and configure shortcuts.</span></span>

  - <span data-ttu-id="ae306-119">**Outlook** Wird verwendet, um das standardmäßige Outlook-Profil eines Benutzers anzupassen, Exchange-Einstellungen anzugeben, Konten hinzuzufügen, Konten zu\\entfernen und Einstellungen zu exportieren sowie Senden von Empfangs Gruppen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ae306-119">**Outlook** Used to customize a user's default Outlook profile, specify Exchange settings, add accounts, remove accounts and export settings, and specify Send\\Receive groups.</span></span>

<span data-ttu-id="ae306-120">Informationen zum OAT finden Sie unter <http://go.microsoft.com/fwlink/p/?linkid=267516>.</span><span class="sxs-lookup"><span data-stu-id="ae306-120">For information about the OCT, see <http://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

