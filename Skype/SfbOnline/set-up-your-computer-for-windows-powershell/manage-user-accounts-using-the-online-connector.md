---
title: Verwalten von Benutzerkonten mit dem Online-Connector
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: a226b0d4-6359-42b8-808d-4b8ab3736d3b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Verwenden Sie das Cmdlet Get-CsOnlineUser in Windows PowerShell, um Informationen zu den Skype for Business Online-Benutzern Ihrer Organisation abzurufen.
ms.openlocfilehash: 370150de08493507d7b401d7907c90f343802d88
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692650"
---
# <a name="manage-user-accounts-using-the-online-connector"></a><span data-ttu-id="41cfe-103">Verwalten von Benutzerkonten mit dem Online-Connector</span><span class="sxs-lookup"><span data-stu-id="41cfe-103">Manage user accounts using the Online Connector</span></span>

## <a name="manage-user-accounts"></a><span data-ttu-id="41cfe-104">Verwalten von Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="41cfe-104">Manage user accounts</span></span>

<span data-ttu-id="41cfe-105">Dieses Thema enthält die folgenden Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="41cfe-105">This topic contains the following sections:</span></span>

- [<span data-ttu-id="41cfe-106">Abrufen von Informationen zu allen Skype for Business Online-Benutzern</span><span class="sxs-lookup"><span data-stu-id="41cfe-106">Return information about all your Skype for Business Online users</span></span>](manage-user-accounts-using-the-online-connector.md#BKAllUsers)

- [<span data-ttu-id="41cfe-107">Abrufen von Informationen zu einem bestimmten Benutzer in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="41cfe-107">Return information for a specific user in Skype for Business Online</span></span>](manage-user-accounts-using-the-online-connector.md#BKSpecificUser)

- [<span data-ttu-id="41cfe-108">Abrufen von bestimmten Informationen zu bestimmten Benutzern in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="41cfe-108">Return specific information for specific users in Skype for Business Online</span></span>](manage-user-accounts-using-the-online-connector.md#BKSpecificUsers)

- [<span data-ttu-id="41cfe-109">Zurückgeben einer gefilterten Liste mit Benutzern in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="41cfe-109">Return a filtered list of users in Skype for Business Online</span></span>](manage-user-accounts-using-the-online-connector.md#BKListofUsers)

> [!NOTE]
> <span data-ttu-id="41cfe-p101">Das Cmdlet **Set-CsUser** ist auch in den Cmdlets enthalten, die für Skype for Business Online-Administratoren zur Verfügung stehen. **Set-CsUser** kann aber zurzeit nicht zum Verwalten von Skype for Business Online verwendet werden, mit einer Ausnahme: Festlegen des Parameters _AudioVideoDisabled_. Wenn Sie versuchen, das Cmdlet mit einem anderen Parameter auszuführen, schlägt dies mit etwa dieser Fehlermeldung fehl: „‚SipAddress' kann nicht festgelegt werden. Dieser Parameter ist auf die Remotemandanten-PowerShell eingeschränkt."</span><span class="sxs-lookup"><span data-stu-id="41cfe-p101">The **Set-CsUser** cmdlet is also included in the set of cmdlets available to Skype for Business Online admins. However, **Set-CsUser** cannot currently be used to manage Skype for Business Online, except for setting the _AudioVideoDisabled_ parameter. If you attempt to run the cmdlet with any other parameter, it will fail with an error message similar to this: Unable to set "SipAddress". This parameter is restricted within Remote Tenant PowerShell.</span></span>

### <a name="return-information-about-all-your-skype-for-business-online-users"></a><span data-ttu-id="41cfe-114">Abrufen von Informationen zu allen Lync Online-Benutzern</span><span class="sxs-lookup"><span data-stu-id="41cfe-114">Return information about all your Skype for Business Online users</span></span>
<span data-ttu-id="41cfe-115"><a name="BKAllUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="41cfe-115"><a name="BKAllUsers"> </a></span></span>

<span data-ttu-id="41cfe-116">Um Informationen zu allen Benutzern abzurufen, die für Skype for Business Online aktiviert sind, rufen Sie das Cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) ohne zusätzliche Parameter auf.</span><span class="sxs-lookup"><span data-stu-id="41cfe-116">To return information about all your users who have been enabled for Skype for Business Online, call the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet without any additional parameters.</span></span>

```PowerShell
Get-CsOnlineUser
```

<span data-ttu-id="41cfe-117">Um Informationen zu einem einzelnen nach dem Zufallsprinzip ausgewählten Benutzer abzurufen (zum Beispiel, um dieses Konto zu Testzwecken zu verwenden), rufen Sie das Cmdlet **Get-CsOnlineUser** auf, und legen Sie den Parameter _ResultSize_ auf „1" fest.</span><span class="sxs-lookup"><span data-stu-id="41cfe-117">To return information for a single, randomly selected user (for example, to use this account for test purposes), call the **Get-CsOnlineUser** cmdlet and set the _ResultSize_ parameter to 1.</span></span>

```PowerShell
Get-CsOnlineUser -ResultSize 1
```

<span data-ttu-id="41cfe-p102">Dies bewirkt, dass das Cmdlet **Get-CsOnlineUser** Informationen für nur einen Benutzer zurückgibt, unabhängig davon, wie viele Benutzer in der Organisation vorhanden sind. Um Informationen für fünf Benutzer abzurufen, legen Sie den Wert des Parameters _ResultSize_ auf „5" fest.</span><span class="sxs-lookup"><span data-stu-id="41cfe-p102">That causes the **Get-CsOnlineUser** cmdlet to return information for just one user, regardless of how many users you have in your organization. To return information for five users, set the value of the _ResultSize_ parameter to 5.</span></span>

```PowerShell
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a><span data-ttu-id="41cfe-120">Abrufen von Informationen zu einem bestimmten Benutzer in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="41cfe-120">Return information for a specific user in Skype for Business Online</span></span>
<span data-ttu-id="41cfe-121"><a name="BKSpecificUser"> </a></span><span class="sxs-lookup"><span data-stu-id="41cfe-121"><a name="BKSpecificUser"> </a></span></span>

<span data-ttu-id="41cfe-p103">Es gibt mehrere Möglichkeiten, beim Aufruf des Cmdlets [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) auf ein bestimmtes Benutzerkonto zu verweisen. Sie können den Active Directory-Domänendienste (AD DS, Active Directory Domain Services)-Anzeigenamen des Benutzers verwenden.</span><span class="sxs-lookup"><span data-stu-id="41cfe-p103">There are multiple ways of referencing a specific user account when calling the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet. You can use the user's Active Directory Domain Services (AD DS) display name.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer"
```

<span data-ttu-id="41cfe-124">Sie können die SIP-Adresse des Benutzers verwenden.</span><span class="sxs-lookup"><span data-stu-id="41cfe-124">You can use the user's SIP address.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

<span data-ttu-id="41cfe-125">Sie können den Benutzerprinzipalnamen (User Principal Name, UPN) des Benutzers verwenden.</span><span class="sxs-lookup"><span data-stu-id="41cfe-125">You can use the user's user principal name (UPN).</span></span>

```PowerShell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a><span data-ttu-id="41cfe-126">Abrufen von bestimmten Informationen zu bestimmten Benutzern in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="41cfe-126">Return specific information for specific users in Skype for Business Online</span></span>
<span data-ttu-id="41cfe-127"><a name="BKSpecificUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="41cfe-127"><a name="BKSpecificUsers"> </a></span></span>

<span data-ttu-id="41cfe-p104">Standardmäßig gibt das Cmdlet [Get-CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) eine große Menge von Informationen zu den einzelnen Skype for Business Online-Benutzerkonten zurück. Wenn Sie sich nur für eine Teilmenge dieser Informationen interessieren, reichen Sie die zurückgegebenen Daten an das Cmdlet **Select-Object** weiter. Dieser Befehl zum Beispiel gibt alle Daten für den Benutzer Ken Myer zurück und beschränkt dann mit dem Cmdlet **Select-Object** die auf dem Bildschirm angezeigten Informationen auf Kens AD DS-Anzeigenamen und Wählplan.</span><span class="sxs-lookup"><span data-stu-id="41cfe-p104">By default, the [Get-CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) cmdlet returns a huge amount of information for each Skype for Business Online user account. If you are interested in only a subset of that information, pipe the returned data to the **Select-Object** cmdlet. For example, this command returns all the data for the user Ken Myer, and then uses the **Select-Object** cmdlet to limit the information displayed onscreen to Ken's AD DS display name and dial plan.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="41cfe-131">Der folgende Befehl gibt die Anzeigenamen und Wählpläne für alle Benutzer zurück.</span><span class="sxs-lookup"><span data-stu-id="41cfe-131">The following command returns the display name and dial plan for all your users.</span></span>

```PowerShell
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="41cfe-132">Mit dem folgenden Befehl können Sie die Eigenschaften eines Skype for Business Online-Benutzerkontos suchen.</span><span class="sxs-lookup"><span data-stu-id="41cfe-132">To find the properties of a Skype for Business Online user account, use the following command.</span></span>

```PowerShell
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a><span data-ttu-id="41cfe-133">Abrufen einer gefilterten Liste mit Benutzern in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="41cfe-133">Return a filtered list of users in Skype for Business Online</span></span>
<span data-ttu-id="41cfe-134"><a name="BKListofUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="41cfe-134"><a name="BKListofUsers"> </a></span></span>

<span data-ttu-id="41cfe-p105">Mit dem Cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) und dem Parameter _LdapFilter_ oder _Filter_ können Sie leicht Informationen zu einer bestimmten Gruppe von Benutzern abrufen. Dieser Befehl zum Beispiel gibt alle Benutzer aus der Finanzabteilung zurück.</span><span class="sxs-lookup"><span data-stu-id="41cfe-p105">By using the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet and the _LdapFilter_ or _Filter_ parameters, you can easily return information about a targeted set of users. For example, this command returns all the users who work in the Finance department.</span></span>

```PowerShell
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a><span data-ttu-id="41cfe-137">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="41cfe-137">Related topics</span></span>
[<span data-ttu-id="41cfe-138">Einrichten Ihres Computers für die Skype for Business Online-Verwaltung mithilfe von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="41cfe-138">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)


