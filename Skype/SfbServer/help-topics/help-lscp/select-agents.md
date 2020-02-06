---
title: Auswählen von Agents
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.RgsSelAgent
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b5cf912b-8273-4c2c-a1e5-f25530b264d0
description: Agents sind Benutzer, die für Antwortgruppen Anrufe vorgesehen sind. Reaktionsgruppen müssen über eine zugewiesene Agentgruppe verfügen, in der die Agents angegeben sind, die Anrufe für die Reaktionsgruppe entgegennehmen können. Eine Möglichkeit zur Erstellung einer Agentgruppe ist die Definition einer benutzerdefinierten Gruppe, indem geeignete Benutzer ausgewählt werden. Berechtigte Benutzer sind für Skype for Business Server und Enterprise-VoIP aktiviert.
ms.openlocfilehash: 2950295bcf78ee2c7c904375d009a8fba085b85f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822308"
---
# <a name="select-agents"></a><span data-ttu-id="9e1c5-106">Auswählen von Agents</span><span class="sxs-lookup"><span data-stu-id="9e1c5-106">Select Agents</span></span>

<span data-ttu-id="9e1c5-107">Agents sind Benutzer, die für Antwortgruppen Anrufe vorgesehen sind.</span><span class="sxs-lookup"><span data-stu-id="9e1c5-107">Agents are users who are designated to answer Response Group calls.</span></span> <span data-ttu-id="9e1c5-108">Reaktionsgruppen müssen über eine zugewiesene Agentgruppe verfügen, in der die Agents angegeben sind, die Anrufe für die Reaktionsgruppe entgegennehmen können.</span><span class="sxs-lookup"><span data-stu-id="9e1c5-108">Response groups must have an assigned agent group that identifies the agents who can receive calls for the response group.</span></span> <span data-ttu-id="9e1c5-109">Eine Möglichkeit zur Erstellung einer Agentgruppe ist die Definition einer benutzerdefinierten Gruppe, indem geeignete Benutzer ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="9e1c5-109">One way to create an agent group is to define a custom group by selecting eligible users.</span></span> <span data-ttu-id="9e1c5-110">Berechtigte Benutzer sind für Skype for Business Server und Enterprise-VoIP aktiviert.</span><span class="sxs-lookup"><span data-stu-id="9e1c5-110">Eligible users are enabled for Skype for Business Server and Enterprise Voice.</span></span>

<span data-ttu-id="9e1c5-111">Verwenden Sie das Dialogfeld **Agents auswählen**, um Benutzer auszuwählen, die einer Agentgruppe hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="9e1c5-111">You use the **Select Agents** dialog box to select users to be added to an agent group.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="9e1c5-112">Referenz zur Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="9e1c5-112">UI Reference</span></span>

<span data-ttu-id="9e1c5-113">In der folgenden Liste werden die Steuerelemente des Dialogfelds **Agents auswählen** beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9e1c5-113">The following list describes the controls in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="9e1c5-114">**Finden Sie** Sucht nach der SIP-Adresse oder dem Anzeigenamen für einen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="9e1c5-114">**Find** Searches for the SIP address or display name for a user.</span></span> <span data-ttu-id="9e1c5-115">Geben Sie die Adresse oder den Namen teilweise oder vollständig ein.</span><span class="sxs-lookup"><span data-stu-id="9e1c5-115">Enter all or part of the address or name.</span></span> <span data-ttu-id="9e1c5-116">Lassen Sie das Suchfeld leer, damit alle Benutzer angezeigt werden, die für Skype for Business Server und Enterprise-VoIP aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="9e1c5-116">Leave the search box empty to display all users who are enabled for Skype for Business Server and Enterprise Voice.</span></span>

- <span data-ttu-id="9e1c5-117">**Maximal anzuzeigende Benutzer** Ändert die Anzahl der zurückgegebenen Ergebnisse, die angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9e1c5-117">**Maximum users to display** Changes the number of returned results that are displayed.</span></span> <span data-ttu-id="9e1c5-118">Verwenden Sie diesen Wert, um die Suche zu begrenzen, falls eine hohe Zahl von Ergebnissen zu erwarten ist.</span><span class="sxs-lookup"><span data-stu-id="9e1c5-118">Use this counter to limit the search if you expect many results.</span></span>

<span data-ttu-id="9e1c5-119">In der folgenden Liste werden die Felder des Dialogfelds **Agents auswählen** beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9e1c5-119">The following list describes the fields in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="9e1c5-120">**Agent** Zeigt die von der Suche zurückgegebenen Benutzernamen an.</span><span class="sxs-lookup"><span data-stu-id="9e1c5-120">**Agent** Displays the user names returned by the search.</span></span>

- <span data-ttu-id="9e1c5-121">**SIP-Adresse** Zeigt die von der Suche zurückgegebenen SIP-Adressen des Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="9e1c5-121">**SIP address** Displays the user SIP addresses returned by the search.</span></span>

- <span data-ttu-id="9e1c5-122">**Telefonie** Zeigt den Wert des für benutzerdefinierten **Telefonie** -Felds an.</span><span class="sxs-lookup"><span data-stu-id="9e1c5-122">**Telephony** Displays the value of the **Telephony** field defined for users.</span></span>

- <span data-ttu-id="9e1c5-123">**Aktiviert** Zeigt den Wert des Felds **Enabled für lync Server** an, das für Benutzerdefiniert ist.</span><span class="sxs-lookup"><span data-stu-id="9e1c5-123">**Enabled** Displays the value of the **Enabled for Lync Server** field defined for users.</span></span>

<span data-ttu-id="9e1c5-124">Ausführliche Informationen zur Verwendung von Agentgruppen finden Sie in der Betriebsdokumentation unter [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx).</span><span class="sxs-lookup"><span data-stu-id="9e1c5-124">For details about working with agent groups, see [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) in the Operations documentation.</span></span>


