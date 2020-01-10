---
title: Verwenden des Office-Anpassungstools (OAT) in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: 'Zusammenfassung: Verwenden des Office-Anpassungstools mit dem Skype for Business-Client'
ms.openlocfilehash: b5c66fee4f6c879c8ded2897b64e63654dd950be
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001595"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a><span data-ttu-id="f5295-103">Verwenden des Office-Anpassungstools (OAT) in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f5295-103">Use the Office Customization Tool (OCT) in Skype for Business Server</span></span>
 
<span data-ttu-id="f5295-104">**Zusammenfassung:** Verwenden des Office-Anpassungstools mit dem Skype for Business-Client</span><span class="sxs-lookup"><span data-stu-id="f5295-104">**Summary:** How to use the Office Customization Tool with the Skype for Business client.</span></span>
  
<span data-ttu-id="f5295-105">Das Office-Anpassungstool (OAT) ist Teil des Setup-Programms und wird als Tool für viele Anpassungen empfohlen.</span><span class="sxs-lookup"><span data-stu-id="f5295-105">The Office Customization Tool (OCT) is part of the Setup program and is the recommended tool for many customizations.</span></span> <span data-ttu-id="f5295-106">Wenn Sie das OAT verwenden, passen Sie Office an, und speichern Sie Ihre Anpassungen in einer MSP-Datei für die Setup Anpassung.</span><span class="sxs-lookup"><span data-stu-id="f5295-106">By using the OCT, you customize Office and save your customizations in a Setup customization .msp file.</span></span> <span data-ttu-id="f5295-107">Sie fügen die Datei im Ordner Updates auf dem Netzwerkinstallationspfad ein.</span><span class="sxs-lookup"><span data-stu-id="f5295-107">You place the file in the Updates folder on the network installation point.</span></span> <span data-ttu-id="f5295-108">Wenn Sie Office installieren, sucht Setup im Ordner Updates nach einer Setupanpassungsdatei und wendet die Anpassungen an.</span><span class="sxs-lookup"><span data-stu-id="f5295-108">When you install Office, Setup looks for a Setup customization file in the Updates folder and applies the customizations.</span></span> <span data-ttu-id="f5295-109">Der Ordner Updates kann nur zum Bereitstellen von Softwareupdates während einer anfänglichen Installation von Office verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f5295-109">The Updates folder can be used only to deploy software updates during an initial installation of Office.</span></span>
  
<span data-ttu-id="f5295-110">Das OAT ist Teil des Setups und wird nur für volumenlizenzierte Versionen des Produkts verwendet.</span><span class="sxs-lookup"><span data-stu-id="f5295-110">The OCT is part of setup and it is only used for volume licensed versions of the product.</span></span> <span data-ttu-id="f5295-111">Sie führen das OAT durch Eingabe `setup.exe /admin` über die Befehlszeile aus dem Stammverzeichnis des Netzwerkinstallationspfads, der die Office-Quelldateien enthält.</span><span class="sxs-lookup"><span data-stu-id="f5295-111">You run the OCT by typing  `setup.exe /admin` at the command line from the root of the network installation point that contains the Office source files.</span></span> <span data-ttu-id="f5295-112">Verwenden Sie beispielsweise folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="f5295-112">For example, use the following:</span></span>
  
 ```console
\\server\share\Office15\setup.exe /admin
```
  
<span data-ttu-id="f5295-113">Administratoren verwenden das OAT zum Erstellen einer Setup Customization. msp-Datei und können die folgenden Bereiche anpassen:</span><span class="sxs-lookup"><span data-stu-id="f5295-113">Administrators use the OCT to create a setup customization .msp file and can customize the following areas:</span></span>
  
- <span data-ttu-id="f5295-114">**Einrichtung** Dient zum Angeben des Standard Installationsspeicherorts auf dem Client und dem Standard Organisationsnamen, zusätzliche Netzwerkinstallationsquellen, Product Key, Endbenutzer-Lizenzvertrag, Anzeigeebene, zu entfernende frühere Versionen von Office, benutzerdefinierte Programme, die während der Installation, Sicherheitseinstellungen und Setup Eigenschaften ausgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f5295-114">**Setup** Used to specify default installation location on the client and default organization name, additional network installation sources, product key, end-user license agreement, display level, earlier versions of Office to remove, custom programs to run during installation, security settings, and Setup properties.</span></span>
    
- <span data-ttu-id="f5295-115">**Funktionen** Wird verwendet, um Benutzereinstellungen zu konfigurieren und die Installation von Office-Features anzupassen.</span><span class="sxs-lookup"><span data-stu-id="f5295-115">**Features** Used to configure user settings and to customize how Office features are installed.</span></span> <span data-ttu-id="f5295-116">Administratoren können das OAT verwenden, um anfängliche Standardwerte für die Office-Anwendungseinstellungen für Benutzer festzulegen.</span><span class="sxs-lookup"><span data-stu-id="f5295-116">Administrators can use the OCT to specify initial default values of Office application settings for users.</span></span> <span data-ttu-id="f5295-117">Benutzer können die meisten Einstellungen nach der Installation ändern.</span><span class="sxs-lookup"><span data-stu-id="f5295-117">Users can modify most of the settings after the installation.</span></span>
    
- <span data-ttu-id="f5295-118">**Zusätzlicher Inhalt** Wird zum Hinzufügen oder Entfernen von Dateien, hinzufügen oder Entfernen von Registrierungseinträgen und Konfigurieren von Tastenkombinationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="f5295-118">**Additional content** Used to add or remove files, add or remove registry entries, and configure shortcuts.</span></span>
    
- <span data-ttu-id="f5295-119">**Outlook** Wird verwendet, um das standardmäßige Outlook-Profil eines Benutzers anzupassen, Exchange-Einstellungen anzugeben, Konten hinzuzufügen, Konten zu entfernen und Einstellungen zu exportieren sowie Übermittlungs-Gruppen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f5295-119">**Outlook** Used to customize a user's default Outlook profile, specify Exchange settings, add accounts, remove accounts and export settings, and specify Send\Receive groups.</span></span>
    
<span data-ttu-id="f5295-120">Informationen zum OAT finden Sie unter [Verwenden des OAT zum Anpassen von Office 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)).</span><span class="sxs-lookup"><span data-stu-id="f5295-120">For information about the OCT, see [Use the OCT to customize Office 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)).</span></span> <span data-ttu-id="f5295-121">Beachten Sie, dass diese Informationen auch für spätere Versionen von Office gelten.</span><span class="sxs-lookup"><span data-stu-id="f5295-121">Note that this information also applies to later versions of Office.</span></span>
  

