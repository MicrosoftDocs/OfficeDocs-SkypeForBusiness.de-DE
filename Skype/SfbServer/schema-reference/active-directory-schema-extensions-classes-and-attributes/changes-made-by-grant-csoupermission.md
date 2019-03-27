---
title: Änderungen, die durch Grant-CsOUPermission in Skype für Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
description: Wenn für die Verwaltung der Business Server Skype delegieren möchten, können Sie angegebenen Organisationseinheiten (OUs) Berechtigungen hinzufügen, damit Mitglieder der Gruppe RTC universellen Gruppen von der Gesamtstruktur erstellt die OUs zugreifen können, ohne dass Sie Mitglied der Gruppe Domänen-Admins.
ms.openlocfilehash: 304f5d905f8839224013a2ce674b98405fd9ce8e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876810"
---
# <a name="changes-made-by-grant-csoupermission-in-skype-for-business-server"></a>Änderungen, die durch Grant-CsOUPermission in Skype für Business Server
 
Wenn für die Verwaltung der Business Server Skype delegieren möchten, können Sie angegebenen Organisationseinheiten (OUs) Berechtigungen hinzufügen, damit Mitglieder der Gruppe RTC universellen Gruppen von der Gesamtstruktur erstellt die OUs zugreifen können, ohne dass Sie Mitglied der Gruppe Domänen-Admins. 
  
Das Cmdlet **Grant-CsOuPermission** gewährt Berechtigungen für Objekte in der angegebenen Organisationseinheit wie in den folgenden Tabellen angegeben.
  
## <a name="granting-permission-for-user-objects"></a>Erteilen von Berechtigungen für User-Objekte

Wenn Sie das **Grant-CsOuPermission** -Cmdlet für User-Objekte in einer Organisationseinheit ausführen, werden Gruppen Berechtigungen wie in der folgenden Tabelle dargestellt erteilt.
  
**Für User-Objekte erteilte Berechtigungen**

|**Gruppe**|**Berechtigung**|**Gilt für**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Verzeichnisänderungen  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Inhalt auflisten  <br/> Alle Eigenschaften lesen  <br/> Leseberechtigungen  <br/> |Nur dieses Objekt  <br/> |
|"RTCuniversalUserReadOnlyGroup"  <br/> |Inhalt auflisten  <br/> Alle Eigenschaften lesen  <br/> Leseberechtigungen  <br/> |Nur dieses Objekt  <br/> |
|"RTCuniversalUserReadOnlyGroup"  <br/> |RTCUserSearchPropertySet lesen  <br/> RTCUserProvisioningPropertySet lesen  <br/> RTCPropertySet lesen  <br/> Öffentliche Informationen lesen  <br/> Allgemeine Informationen lesen  <br/> Benutzer Kontoeinschränkungen lesen  <br/> |Untergeordnete User-Objekte  <br/> |
|RTCUniversalUserAdmins  <br/> |Schreiben von RTCUserSearchPropertySet  <br/> Schreiben Sie "msexchucvoicemailsettings"  <br/> Schreiben von RTCUserProvisioningPropertySet  <br/> Schreiben von RTCPropertySet  <br/> ProxyAddresses schreiben  <br/> |Untergeordnete User-Objekte  <br/> |
   
## <a name="granting-permission-for-computer-objects"></a>Erteilen von Berechtigungen für Computerobjekte

Wenn Sie das **Grant-CsOuPermission** -Cmdlet für Computer-Objekte in einer Organisationseinheit ausführen, werden Gruppen Berechtigungen wie in der folgenden Tabelle dargestellt erteilt.
  
**Für Computer-Objekte erteilte Berechtigungen**

|**Gruppe**|**Berechtigung**|**Gilt für**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Verzeichnisänderungen  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Inhalt auflisten  <br/> Alle Eigenschaften lesen  <br/> Leseberechtigungen  <br/> |Nur dieses Objekt  <br/> |
|"RTCuniversalUserReadOnlyGroup"  <br/> |Inhalt auflisten  <br/> Alle Eigenschaften lesen  <br/> Leseberechtigungen  <br/> |Nur dieses Objekt  <br/> |
|"RTCuniversalUserReadOnlyGroup"  <br/> |Öffentliche Informationen lesen  <br/> Lesen Sie überprüft-DNS-Host-Name  <br/> |Untergeordnete Computer-Objekte  <br/> |
|RTCUniversalUserAdmins  <br/> |Öffentliche Informationen lesen  <br/> Lesen Sie überprüft-DNS-Host-Name  <br/> |Untergeordnete Computer-Objekte  <br/> |
   
## <a name="granting-permission-for-contact-or-appcontact-objects"></a>Erteilen von Berechtigungen für Contact oder AppContact-Objekte

Wenn Sie das **Grant-CsOuPermission** -Cmdlet für Contact- oder AppContact-Objekte in einer Organisationseinheit ausführen, werden Gruppen Berechtigungen erteilt, wie in der folgenden Tabelle dargestellt.
  
**Für Contact- oder AppContact-Objekte erteilte Berechtigungen**

|**Gruppe**|**Berechtigung**|**Gilt für**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Verzeichnisänderungen  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Inhalt auflisten  <br/> Alle Eigenschaften lesen  <br/> Leseberechtigungen  <br/> |Nur dieses Objekt  <br/> |
|"RTCuniversalUserReadOnlyGroup"  <br/> |Inhalt auflisten  <br/> Alle Eigenschaften lesen  <br/> Leseberechtigungen  <br/> |Nur dieses Objekt  <br/> |
|"RTCuniversalUserReadOnlyGroup"  <br/> |RTCUserSearchPropertySet lesen  <br/> RTCUserProvisioningPropertySet lesen  <br/> RTCPropertySet lesen  <br/> Öffentliche Informationen lesen  <br/> Allgemeine Informationen lesen  <br/> Lesen Sie persönliche Informationen  <br/> Benutzer Kontoeinschränkungen lesen  <br/> |Untergeordnete Contact-Objekte  <br/> |
|RTCUniversalUserAdmins  <br/> |Schreiben von RTCUserSearchPropertySet  <br/> "Otheripphone" schreiben  <br/> DisplayName schreiben  <br/> Schreiben Sie Beschreibung  <br/> TelephoneNumber schreiben  <br/> Schreiben Sie "msexchucvoicemailsettings"  <br/> Schreiben von RTCUserProvisioningPropertySet  <br/> Schreiben von RTCPropertySet  <br/> ProxyAddresses schreiben  <br/> |Untergeordnete Contact-Objekte  <br/> |
   
## <a name="granting-permission-for-device-objects"></a>Erteilen von Berechtigungen für Device-Objekte

Wenn Sie das **Grant-CsOuPermission** -Cmdlet für Device-Objekte in einer Organisationseinheit ausführen, werden Gruppen Berechtigungen wie in der folgenden Tabelle dargestellt erteilt.
  
**Für Device-Objekte erteilte Berechtigungen**

|**Gruppe**|**Berechtigung**|**Gilt für**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Verzeichnisänderungen  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Inhalt auflisten  <br/> Alle Eigenschaften lesen  <br/> Leseberechtigungen  <br/> |Nur dieses Objekt  <br/> |
|"RTCuniversalUserReadOnlyGroup"  <br/> |Inhalt auflisten  <br/> Alle Eigenschaften lesen  <br/> Leseberechtigungen  <br/> |Nur dieses Objekt  <br/> |
|"RTCuniversalUserReadOnlyGroup"  <br/> |RTCUserSearchPropertySet lesen  <br/> RTCUserProvisioningPropertySet lesen  <br/> RTCPropertySet lesen  <br/> Öffentliche Informationen lesen  <br/> Lesen Sie persönliche Informationen  <br/> Allgemeine Informationen lesen  <br/> Benutzer Kontoeinschränkungen lesen  <br/> |Untergeordnete Contact-Objekte  <br/> |
|RTCUniversalUserAdmins  <br/> |Untergeordnetes Objekt erstellen  <br/> Untergeordnetes Objekt löschen  <br/> Struktur löschen  <br/> |Kontakt  <br/> |
|RTCUniversalUserAdmins  <br/> |DisplayName schreiben  <br/> Schreiben Sie Beschreibung  <br/> TelephoneNumber schreiben  <br/> |Untergeordnete User-Objekte  <br/> |
|RTCUniversalUserAdmins  <br/> |Schreiben von RTCUserSearchPropertySet  <br/> "Otheripphone" schreiben  <br/> DisplayName schreiben  <br/> Schreiben Sie Beschreibung  <br/> TelephoneNumber schreiben  <br/> Schreiben Sie "msexchucvoicemailsettings"  <br/> Schreiben von RTCUserProvisioningPropertySet  <br/> Schreiben von RTCPropertySet  <br/> ProxyAddresses schreiben  <br/> |Untergeordnete Contact-Objekte  <br/> |
   
## <a name="granting-permission-for-inetorgperson-objects"></a>Erteilen von Berechtigungen für InetOrgPerson-Objekte

Wenn Sie das **Grant-CsOuPermission** -Cmdlet für InetOrgPerson-Objekte in einer Organisationseinheit ausführen, werden Gruppen Berechtigungen wie in der folgenden Tabelle dargestellt erteilt.
  
**Für InetOrgPerson-Objekte erteilte Berechtigungen**

|**Gruppe**|**Berechtigung**|**Gilt für**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Verzeichnisänderungen  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Inhalt auflisten  <br/> Alle Eigenschaften lesen  <br/> Leseberechtigungen  <br/> |Nur dieses Objekt  <br/> |
|"RTCuniversalUserReadOnlyGroup"  <br/> |Inhalt auflisten  <br/> Alle Eigenschaften lesen  <br/> Leseberechtigungen  <br/> |Nur dieses Objekt  <br/> |
|"RTCuniversalUserReadOnlyGroup"  <br/> |RTCUserSearchPropertySet lesen  <br/> RTCUserProvisioningPropertySet lesen  <br/> RTCPropertySet lesen  <br/> Lesen Sie persönliche Informationen  <br/> Öffentliche Informationen lesen  <br/> Allgemeine Informationen lesen  <br/> Benutzer Kontoeinschränkungen lesen  <br/> |Untergeordnete InetOrgPerson-Objekte  <br/> |
|RTCUniversalUserAdmins  <br/> |Schreiben von RTCUserSearchPropertySet  <br/> Schreiben von RTCUserProvisioningPropertySet  <br/> Schreiben von RTCPropertySet  <br/> ProxyAddresses schreiben  <br/> |Untergeordnete InetOrgPerson-Objekte  <br/> |
   

