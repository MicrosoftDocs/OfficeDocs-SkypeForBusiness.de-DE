---
title: Von Grant-CsOUPermission in Skype for Business Server vorgenommene Änderungen
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
description: Um Skype for Business Server Verwaltung zu delegieren, können Sie Berechtigungen zu bestimmten Organisationseinheiten (OUs) hinzufügen, sodass Mitglieder der durch die Gesamtstrukturvorbereitung erstellten universellen RTC-Gruppen auf die Organisationseinheiten zugreifen können, ohne Mitglieder der Gruppe "Domänenadministratoren" zu sein.
ms.openlocfilehash: f700b03f95be05e00d4e5eb032d9dd50ceb1352b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613905"
---
# <a name="changes-made-by-grant-csoupermission-in-skype-for-business-server"></a>Von Grant-CsOUPermission in Skype for Business Server vorgenommene Änderungen
 
Um Skype for Business Server Verwaltung zu delegieren, können Sie Berechtigungen zu bestimmten Organisationseinheiten (OUs) hinzufügen, sodass Mitglieder der durch die Gesamtstrukturvorbereitung erstellten universellen RTC-Gruppen auf die Organisationseinheiten zugreifen können, ohne Mitglieder der Gruppe "Domänenadministratoren" zu sein. 
  
Mit dem **Grant-CsOuPermission**-Cmdlet werden Objekten in der angegebenen Organisationseinheit Berechtigungen gemäß der folgenden Tabellen erteilt.
  
## <a name="granting-permission-for-user-objects"></a>Erteilen von Berechtigungen für User-Objekte

Wenn Sie das Cmdlet **Grant-CsOuPermission** für Benutzerobjekte in einer OE ausführen, werden Gruppen Berechtigungen gewährt, wie in der folgenden Tabelle dargestellt.
  
**Für <c0>User</c0>-Objekte erteilte Berechtigungen**

|**Gruppe**|**Berechtigung**|**Gilt für**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Verzeichnisänderungen replizieren  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Inhalt auflisten  <br/> Alle Eigenschaften lesen  <br/> Leseberechtigungen  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Inhalt auflisten  <br/> Alle Eigenschaften lesen  <br/> Leseberechtigungen  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Read RTCUserSearchPropertySet  <br/> Read RTCUserProvisioningPropertySet  <br/> Read RTCPropertySet  <br/> Read Public-Information  <br/> Read General-Information  <br/> Read User-Account-Restrictions  <br/> |Untergeordnete User-Objekte  <br/> |
|RTCUniversalUserAdmins  <br/> |Write RTCUserSearchPropertySet  <br/> Write msExchUCVoiceMailSettings  <br/> Write RTCUserProvisioningPropertySet  <br/> Write RTCPropertySet  <br/> Write proxyAddresses  <br/> |Untergeordnete User-Objekte  <br/> |
   
## <a name="granting-permission-for-computer-objects"></a>Erteilen von Berechtigungen für Computer-Objekte

Wenn Sie das Cmdlet **Grant-CsOuPermission** für Computerobjekte in einer OE ausführen, werden Gruppen Berechtigungen gewährt, wie in der folgenden Tabelle dargestellt.
  
**Für <c0>Computer</c0>-Objekte erteilte Berechtigungen**

|**Gruppe**|**Berechtigung**|**Gilt für**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Verzeichnisänderungen replizieren  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Inhalt auflisten  <br/> Alle Eigenschaften lesen  <br/> Leseberechtigungen  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Inhalt auflisten  <br/> Alle Eigenschaften lesen  <br/> Leseberechtigungen  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Read Public-Information  <br/> Read Validated-DNS-Host-Name  <br/> |Untergeordnete Computer-Objekte  <br/> |
|RTCUniversalUserAdmins  <br/> |Read Public-Information  <br/> Read Validated-DNS-Host-Name  <br/> |Untergeordnete Computer-Objekte  <br/> |
   
## <a name="granting-permission-for-contact-or-appcontact-objects"></a>Erteilen von Berechtigungen für Contact oder AppContact-Objekte

Wenn Sie das Cmdlet **Grant-CsOuPermission** für Contact-Objekte oder AppContact-Objekte in einer ORGANISATIONSeinheit ausführen, werden Gruppen Berechtigungen gewährt, wie in der folgenden Tabelle dargestellt.
  
**Für <c0>Contact</c0>- oder <c1>AppContact</c1>-Objekte erteilte Berechtigungen**

|**Gruppe**|**Berechtigung**|**Gilt für**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Verzeichnisänderungen replizieren  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Inhalt auflisten  <br/> Alle Eigenschaften lesen  <br/> Leseberechtigungen  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Inhalt auflisten  <br/> Alle Eigenschaften lesen  <br/> Leseberechtigungen  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Read RTCUserSearchPropertySet  <br/> Read RTCUserProvisioningPropertySet  <br/> Read RTCPropertySet  <br/> Read Public-Information  <br/> Read General-Information  <br/> Read Personal-Information  <br/> Read User-Account-Restrictions  <br/> |Untergeordnete Contact-Objekte  <br/> |
|RTCUniversalUserAdmins  <br/> |Write RTCUserSearchPropertySet  <br/> Write otherIpPhone  <br/> Write displayName  <br/> Write description  <br/> Write telephoneNumber  <br/> Write msExchUCVoiceMailSettings  <br/> Write RTCUserProvisioningPropertySet  <br/> Write RTCPropertySet  <br/> Write proxyAddresses  <br/> |Untergeordnete Contact-Objekte  <br/> |
   
## <a name="granting-permission-for-device-objects"></a>Erteilen von Berechtigungen für Device-Objekte

Wenn Sie das Cmdlet **Grant-CsOuPermission für Device-Objekte** in einer ORGANISATIONSeinheit ausführen, werden Gruppen Berechtigungen gewährt, wie in der folgenden Tabelle dargestellt.
  
**Für <c0>Device</c0>-Objekte erteilte Berechtigungen**

|**Gruppe**|**Berechtigung**|**Gilt für**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Verzeichnisänderungen replizieren  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Inhalt auflisten  <br/> Alle Eigenschaften lesen  <br/> Leseberechtigungen  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Inhalt auflisten  <br/> Alle Eigenschaften lesen  <br/> Leseberechtigungen  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Read RTCUserSearchPropertySet  <br/> Read RTCUserProvisioningPropertySet  <br/> Read RTCPropertySet  <br/> Read Public-Information  <br/> Read Personal-Information  <br/> Read General-Information  <br/> Read User-Account-Restrictions  <br/> |Untergeordnete Contact-Objekte  <br/> |
|RTCUniversalUserAdmins  <br/> |Untergeordnetes Element erstellen  <br/> Untergeordnetes Element löschen  <br/> Struktur löschen  <br/> |Kontakt  <br/> |
|RTCUniversalUserAdmins  <br/> |Write displayName  <br/> Write description  <br/> Write telephoneNumber  <br/> |Untergeordnete User-Objekte  <br/> |
|RTCUniversalUserAdmins  <br/> |Write RTCUserSearchPropertySet  <br/> Write otherIpPhone  <br/> Write displayName  <br/> Write description  <br/> Write telephoneNumber  <br/> Write msExchUCVoiceMailSettings  <br/> Write RTCUserProvisioningPropertySet  <br/> Write RTCPropertySet  <br/> Write proxyAddresses  <br/> |Untergeordnete Contact-Objekte  <br/> |
   
## <a name="granting-permission-for-inetorgperson-objects"></a>Erteilen von Berechtigungen für InetOrgPerson-Objekte

Wenn Sie das Cmdlet **Grant-CsOuPermission** für InetOrgPerson-Objekte in einer OU ausführen, erhalten Gruppen Berechtigungen, wie in der folgenden Tabelle dargestellt.
  
**Für <c0>InetOrgPerson</c0>-Objekte erteilte Berechtigungen**

|**Gruppe**|**Berechtigung**|**Gilt für**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Verzeichnisänderungen replizieren  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Inhalt auflisten  <br/> Alle Eigenschaften lesen  <br/> Leseberechtigungen  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Inhalt auflisten  <br/> Alle Eigenschaften lesen  <br/> Leseberechtigungen  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Read RTCUserSearchPropertySet  <br/> Read RTCUserProvisioningPropertySet  <br/> Read RTCPropertySet  <br/> Read Personal-Information  <br/> Read Public-Information  <br/> Read General-Information  <br/> Read User-Account-Restrictions  <br/> |Untergeordnete inetOrgPerson-Objekte  <br/> |
|RTCUniversalUserAdmins  <br/> |Write RTCUserSearchPropertySet  <br/> Write RTCUserProvisioningPropertySet  <br/> Write RTCPropertySet  <br/> Write proxyAddresses  <br/> |Untergeordnete inetOrgPerson-Objekte  <br/> |
   

