---
title: Verwalten von Benutzerkonten
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Use the Get-CsOnlineUser cmdlet in Windows PowerShell to get information about your organization's Skype for Business Online users.
ms.openlocfilehash: 8f6ca618925b070e1d42a215cb9afb076a1e8197
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32226407"
---
# <a name="manage-user-accounts"></a><span data-ttu-id="80cf5-103">Verwalten von Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="80cf5-103">Manage user accounts</span></span>

## <a name="manage-user-accounts"></a><span data-ttu-id="80cf5-104">Verwalten von Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="80cf5-104">Manage user accounts</span></span>

<span data-ttu-id="80cf5-105">Dieses Thema enthält die folgenden Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="80cf5-105">This topic contains the following sections:</span></span>

- [<span data-ttu-id="80cf5-106">Abrufen von Informationen zu allen Skype for Business Online-Benutzern</span><span class="sxs-lookup"><span data-stu-id="80cf5-106">Return information about all your Skype for Business Online users</span></span>](manage-user-accounts.md#BKMKReturnInfoAboutAllUsers)

- [<span data-ttu-id="80cf5-107">Abrufen von Informationen zu einem bestimmten Benutzer in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="80cf5-107">Return information for a specific user in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturnInfoSpecificUser)

- [<span data-ttu-id="80cf5-108">Abrufen von bestimmten Informationen zu bestimmten Benutzern in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="80cf5-108">Return specific information for specific users in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturninfoSpecificUsers)

- [<span data-ttu-id="80cf5-109">Abrufen einer gefilterten Liste mit Benutzern in Skype for Business Online </span><span class="sxs-lookup"><span data-stu-id="80cf5-109">Return a filtered list of users in Skype for Business Online </span></span>](manage-user-accounts.md#BKMKReturnFilteredListofUsers)

> [!NOTE]
> <span data-ttu-id="80cf5-p101">Das Cmdlet **Set-CsUser** ist auch in den Cmdlets enthalten, die für Skype for Business Online-Administratoren zur Verfügung stehen. **Set-CsUser** kann aber zurzeit nicht zum Verwalten von Skype for Business Online verwendet werden, mit einer Ausnahme: Festlegen des Parameters _AudioVideoDisabled_. Wenn Sie versuchen, das Cmdlet mit einem anderen Parameter auszuführen, schlägt dies mit etwa dieser Fehlermeldung fehl: „‚SipAddress' kann nicht festgelegt werden. Dieser Parameter ist auf die Remotemandanten-PowerShell eingeschränkt."</span><span class="sxs-lookup"><span data-stu-id="80cf5-p101">The **Set-CsUser** cmdlet is also included in the set of cmdlets available to Skype for Business Online admins. However, **Set-CsUser** cannot currently be used to manage Skype for Business Online, except for setting the _AudioVideoDisabled_ parameter. If you attempt to run the cmdlet with any other parameter, it will fail with an error message similar to this: Unable to set "SipAddress". This parameter is restricted within Remote Tenant PowerShell.</span></span>

### <a name="return-information-about-all-your-skype-for-business-online-users"></a><span data-ttu-id="80cf5-114">Abrufen von Informationen zu allen Lync Online-Benutzern</span><span class="sxs-lookup"><span data-stu-id="80cf5-114">Return information about all your Skype for Business Online users</span></span>
<span data-ttu-id="80cf5-115"><a name="BKMKReturnInfoAboutAllUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="80cf5-115"></span></span>

<span data-ttu-id="80cf5-116">Um Informationen zu allen Benutzern abzurufen, die für Skype for Business Online aktiviert sind, rufen Sie das Cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) ohne zusätzliche Parameter auf.</span><span class="sxs-lookup"><span data-stu-id="80cf5-116">To return information about all your users who have been enabled for Skype for Business Online, call the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet without any additional parameters.</span></span>

```
Get-CsOnlineUser
```

<span data-ttu-id="80cf5-117">Um Informationen zu einem einzelnen nach dem Zufallsprinzip ausgewählten Benutzer abzurufen (zum Beispiel, um dieses Konto zu Testzwecken zu verwenden), rufen Sie das Cmdlet **Get-CsOnlineUser** auf, und legen Sie den Parameter _ResultSize_ auf „1" fest.</span><span class="sxs-lookup"><span data-stu-id="80cf5-117">To return information for a single, randomly selected user (for example, to use this account for test purposes), call the **Get-CsOnlineUser** cmdlet and set the _ResultSize_ parameter to 1.</span></span>

```
Get-CsOnlineUser -ResultSize 1
```

<span data-ttu-id="80cf5-p102">Dies bewirkt, dass das Cmdlet **Get-CsOnlineUser** Informationen für nur einen Benutzer zurückgibt, unabhängig davon, wie viele Benutzer in der Organisation vorhanden sind. Um Informationen für fünf Benutzer abzurufen, legen Sie den Wert des Parameters _ResultSize_ auf „5" fest.</span><span class="sxs-lookup"><span data-stu-id="80cf5-p102">That causes the **Get-CsOnlineUser** cmdlet to return information for just one user, regardless of how many users you have in your organization. To return information for five users, set the value of the _ResultSize_ parameter to 5.</span></span>

```
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a><span data-ttu-id="80cf5-120">Abrufen von Informationen zu einem bestimmten Benutzer in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="80cf5-120">Return information for a specific user in Skype for Business Online</span></span>
<span data-ttu-id="80cf5-121"><a name="BKMKReturnInfoSpecificUser"> </a></span><span class="sxs-lookup"><span data-stu-id="80cf5-121"></span></span>

<span data-ttu-id="80cf5-p103">Es gibt mehrere Möglichkeiten, beim Aufruf des Cmdlets [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) auf ein bestimmtes Benutzerkonto zu verweisen. Sie können den Active Directory-Domänendienste (AD DS, Active Directory Domain Services)-Anzeigenamen des Benutzers verwenden.</span><span class="sxs-lookup"><span data-stu-id="80cf5-p103">There are multiple ways of referencing a specific user account when calling the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet. You can use the user's Active Directory Domain Services (AD DS) display name.</span></span>

```
Get-CsOnlineUser -Identity "Ken Myer"
```

<span data-ttu-id="80cf5-124">Sie können die SIP-Adresse des Benutzers verwenden.</span><span class="sxs-lookup"><span data-stu-id="80cf5-124">You can use the user's SIP address.</span></span>

```
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

<span data-ttu-id="80cf5-125">Sie können den Benutzerprinzipalnamen (User Principal Name, UPN) des Benutzers verwenden.</span><span class="sxs-lookup"><span data-stu-id="80cf5-125">You can use the user's user principal name (UPN).</span></span>

```
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a><span data-ttu-id="80cf5-126">Abrufen von bestimmten Informationen zu bestimmten Benutzern in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="80cf5-126">Return specific information for specific users in Skype for Business Online</span></span>
<span data-ttu-id="80cf5-127"><a name="BKMKReturninfoSpecificUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="80cf5-127"></span></span>

<span data-ttu-id="80cf5-p104">Standardmäßig gibt das Cmdlet [Get-CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) eine große Menge von Informationen zu den einzelnen Skype for Business Online-Benutzerkonten zurück. Wenn Sie sich nur für eine Teilmenge dieser Informationen interessieren, reichen Sie die zurückgegebenen Daten an das Cmdlet **Select-Object** weiter. Dieser Befehl zum Beispiel gibt alle Daten für den Benutzer Ken Myer zurück und beschränkt dann mit dem Cmdlet **Select-Object** die auf dem Bildschirm angezeigten Informationen auf Kens AD DS-Anzeigenamen und Wählplan.</span><span class="sxs-lookup"><span data-stu-id="80cf5-p104">By default, the [Get-CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) cmdlet returns a huge amount of information for each Skype for Business Online user account. If you are interested in only a subset of that information, pipe the returned data to the **Select-Object** cmdlet. For example, this command returns all the data for the user Ken Myer, and then uses the **Select-Object** cmdlet to limit the information displayed onscreen to Ken's AD DS display name and dial plan.</span></span>

```
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="80cf5-131">Der folgende Befehl gibt die Anzeigenamen und Wählpläne für alle Benutzer zurück.</span><span class="sxs-lookup"><span data-stu-id="80cf5-131">The following command returns the display name and dial plan for all your users.</span></span>

```
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="80cf5-132">Mit dem folgenden Befehl können Sie die Eigenschaften eines Skype for Business Online-Benutzerkontos suchen.</span><span class="sxs-lookup"><span data-stu-id="80cf5-132">To find the properties of a Skype for Business Online user account, use the following command.</span></span>

```
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a><span data-ttu-id="80cf5-133">Abrufen einer gefilterten Liste mit Benutzern in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="80cf5-133">Return a filtered list of users in Skype for Business Online</span></span>
<span data-ttu-id="80cf5-134"><a name="BKMKReturnFilteredListofUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="80cf5-134"></span></span>

<span data-ttu-id="80cf5-p105">Mit dem Cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) und dem Parameter _LdapFilter_ oder _Filter_ können Sie leicht Informationen zu einer bestimmten Gruppe von Benutzern abrufen. Dieser Befehl zum Beispiel gibt alle Benutzer aus der Finanzabteilung zurück.</span><span class="sxs-lookup"><span data-stu-id="80cf5-p105">By using the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet and the _LdapFilter_ or _Filter_ parameters, you can easily return information about a targeted set of users. For example, this command returns all the users who work in the Finance department.</span></span>

```
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a><span data-ttu-id="80cf5-137">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="80cf5-137">Related topics</span></span>
[<span data-ttu-id="80cf5-138">Einrichten des Computers für Skype für das Business online Management mithilfe von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="80cf5-138">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)


