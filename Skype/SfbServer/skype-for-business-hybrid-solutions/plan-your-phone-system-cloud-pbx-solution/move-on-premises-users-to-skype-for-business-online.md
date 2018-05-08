---
title: Migrieren von lokalen Benutzern zu Skype für Business Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 2475674a-f592-4fa8-ae99-f71cbea54dc0
description: 'Zusammenfassung: Informationen zum Verschieben von lokalen Benutzern Skype für Business Online.'
ms.openlocfilehash: 09eb62c59ccea1334d7f565a0a49989bff72745b
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="move-on-premises-users-to-skype-for-business-online"></a>Migrieren von lokalen Benutzern zu Skype für Business Online
 
**Zusammenfassung:** Informationen zum Verschieben von lokalen Benutzern zu Skype für Business Online.
  
> [!CAUTION]
> Lync Phone Edition-Geräte MÜSSEN in Ihrer lokalen Umgebung auf die minimal erforderliche Firmware aktualisiert werden, BEVOR nach Skype for Business Online umgezogen wird. Wenn Sie Ihre Benutzer vor einer Aktualisierung der Firma von der lokalen Verwendung zur Onlinebereitstellung übertragen, können diese Benutzer mit ihren Telefonen keine Verbindung herstellen. Um dieses Problem zu beheben, müssen die Benutzer zur lokalen Umgebung zurückübertragen werden, damit ihre Telefone dort auf die minimal erforderliche Firmware aktualisiert werden. VERSUCHEN SIE NICHT; VOR DEM ZURÜCKÜBERTRAGEN DER BENUTZER ZU IHRER LOKALEN UMGEBUNG AUF DIE MINIMAL ERFORDERLICHE FIRMWARE ZU AKTUALISIEREN ODER EIN HARDRESET DER TELEFONE DURCHZUFÜHREN.
Wenn ein Hardreset durchgeführt wird, während das Gerät nicht mit der minimal erforderlichen Firmware ausgestattet ist, nutzt das Telefon standardmäßig die PIN-Authentifizierung, die in Skype for Business Online nicht unterstützt wird. Weitere Informationen finden Sie unter [Abrufen von Telefonen für Skype für Business Online](https://support.office.com/en-us/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US).
  
Dies ist ein optionaler Schritt, der erforderlich ist, nur, wenn Sie lokale Benutzer auf Skype für Business Online verschieben. Bevor Sie beginnen, um Benutzer zu Skype für Business Online zu verschieben, überprüfen Sie, dass die Skype für Business Online Connector (Windows PowerShell-Modul) auf Front-End-Servern bereitgestellt wird. Wenn es nicht der Fall ist, können Sie es aus [dem Downloadcenter](https://www.microsoft.com/en-us/download/details.aspx?id=39366)herunterladen. Für die Vorbereitung Ihres AD müssen Sie Azure AD Connect konfigurieren. Die Version von AAD, die Sie verwenden, muss wenigstens Version 1.0.9125.0 oder höher sein. Wenn Sie mit einer früheren Version der AAD Connect-Werkzeuge oder DirSync arbeiten, führen Sie ein Upgrade auf die unterstützte Version durch. Sie können aber auch ein Upgrade Ihrer aktuellen Installation durchführen und alle benutzerdefinierten Regeln beibehalten, die Sie in Ihrer Umgebung definiert haben.
  
Verschieben von Benutzern, die entweder Skype für Business Server-Systemsteuerung oder Skype für Business Server-Verwaltungsshell in der lokalen Bereitstellung verwenden, jedoch benötigen Sie Administratorberechtigungen für Ihre Office 365-Bereitstellung.
  
## <a name="moving-users-by-using-skype-for-business-control-panel"></a>Verschieben von Benutzern mithilfe von Skype für die Business-Systemsteuerung

### <a name="to-move-a-user-to-skype-for-business-online"></a>Zum Verschieben eines Benutzers zu Skype für Business Online

1. Von einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder der csadministrator zugewiesen ist, melden Sie sich an einem beliebigen Computer in Ihrer internen Bereitstellung mit Skype für Business Server oder auf mindestens Skype für die Business Server-Verwaltungstools installiert.
    
2. Öffnen Sie auf das Startmenü oder desktop-Verknüpfung die Skype Business Server-Systemsteuerung.
    
    Sie können auch die Skype Business Server-Systemsteuerung zugreifen, indem die Admin-URL verwenden, wenn Sie eine konfiguriert haben.
    
3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.
    
4. Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das aktiviert werden soll und klicken Sie dann auf **Suchen**.
    
5. Klicken Sie auf den Benutzer, auf das **Aktionsmenü** und anschließend auf **Ausgewählte Benutzer zu Skype for Business Online verschieben**.
    
6. Lesen Sie die Informationen auf der Seite **Verschieben von Benutzern zu Skype for Business Online** und klicken Sie dann auf **Weiter**.
    
7. Auf der nächsten Seite Wenn Sie nicht noch zu Office 365 angemeldet sind, klicken Sie auf **Anmelden bei Office 365**, Anmeldeinformationen Sie Ihre, und klicken Sie auf **OK** und **Weiter**.
    
8. Vergewissern Sie sich, dass die Anzahl der zu verschiebenden Benutzer richtig ist, und klicken Sie dann auf **Weiter**.
    
9. Lesen Sie auf der nächsten Seite die Ergebnisse durch und klicken Sie dann auf **Schließen**.
    
## <a name="moving-users-by-using-skype-for-business-server-management-shell"></a>Verschieben von Benutzern mithilfe von Skype für Business Server-Verwaltungsshell

Um einen lokalen Benutzer in Ihrer Skype für Business Online-Mandanten zu verschieben, führen Sie die folgenden Cmdlets in der Skype für Business Server-Verwaltungsshell, verwenden die Administratoranmeldeinformationen für Ihre Microsoft Office 365-Mandanten. Ersetzen Sie „benutzername@contoso.com“ mit den Informationen des zu verschiebenden Benutzers.
  
```
$creds=Get-Credential
```

```
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
```

Das Format der URL für der **HostedMigrationOverrideUrl** -Parameter die URL auf den Pool sein muss, auf dem der Migration gehosteten Dienst wird, im folgenden Format ausgeführt, angegeben: _Https://\<Pool-FQDN\>/HostedMigration/ hostedmigrationService.svc_.
  
Die URL der Migration gehosteter Dienst können Sie bestimmen, indem Sie die URL für die Skype für Business Online Admin Center für Ihre Office 365-mandantenkontos anzeigen.
  
> [!NOTE]
> Bei der URL muss die Groß-/Kleinschreibung beachtet werden. 
  
### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a>So ermitteln Sie die URL des gehosteten Migrationsdiensts für Ihren Office 365-Mandanten

1. Melden Sie sich als Administrator bei Ihrem Office 365-Mandanten an.
    
2. Öffnen Sie das **Skype for Business Admin Center**.
    
3. Wenn das **Skype for Business Admin Center** angezeigt wird, wählen Sie die URL in der Adressliste bis zu **lync.com** aus und kopieren Sie sie. Eine Beispiel-URL sieht ähnlich wie die folgende aus:
    
     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`
    
4. Ersetzen Sie **webdir** in der URL durch **admin**, womit Sie folgendes Ergebnis erhalten: 
    
     `https://admin0a.online.lync.com`
    
5. Fügen Sie dann folgende Zeichenfolge an die URL an: **/HostedMigration/hostedmigrationService.svc**.
    
    Ergebnis-URL, die den Wert der **HostedMigrationOverrideUrl**ist, sollte wie folgt aussehen:
    
     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationService.svc`
    

