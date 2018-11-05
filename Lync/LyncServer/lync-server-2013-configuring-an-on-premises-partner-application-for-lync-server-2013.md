---
title: Konfigurieren einer lokalen Partneranwendung für Microsoft Lync Server 2013
TOCTitle: Konfigurieren einer lokalen Partneranwendung für Microsoft Lync Server 2013
ms:assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204975(v=OCS.15)
ms:contentKeyID: 49294285
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren einer lokalen Partneranwendung für Microsoft Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-04_

Nachdem Sie das Zertifikat "OAuthTokenIssuer" zugewiesen haben, müssen Sie Ihre Microsoft Lync Server 2013-Partneranwendungen konfigurieren. (Bei der hier vorgestellten Methode werden sowohl Microsoft Exchange Server 2013 als auch Microsoft SharePoint als Partneranwendungen konfiguriert.) Zur Konfiguration einer lokalen Partneranwendung müssen Sie zuerst das folgende Windows PowerShell-Skript kopieren und den Code dann in einen Text-Editor Ihrer Wahl einfügen:

    if ((Get-CsPartnerApplication -ErrorAction SilentlyContinue) -ne $Null)
       {
           Remove-CsPartnerApplication app
       }
    
    $exch = Get-CsPartnerApplication microsoft.exchange -ErrorAction SilentlyContinue
            
    if ($exch -eq $null)
       {
          New-CsPartnerApplication -Identity microsoft.exchange -MetadataUrl https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 -ApplicationTrustLevel Full 
        }
    else
        {
           if ($exch.ApplicationIdentifier -ne "00000002-0000-0ff1-ce00-000000000000")
              {
                 Remove-CsPartnerApplication microsoft.exchange
    New-CsPartnerApplication -Identity microsoft.exchange -MetadataUrl https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 -ApplicationTrustLevel Full 
               }
            else
               {
                 Set-CsPartnerApplication -Identity microsoft.exchange -ApplicationTrustLevel Full 
               }
         }
    
    $shp = Get-CsPartnerApplication microsoft.sharepoint -ErrorAction SilentlyContinue
            
    if ($shp -eq $null)
       {
          New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx -ApplicationTrustLevel Full 
        }
    else
        {
           if ($shp.ApplicationIdentifier -ne "00000003-0000-0ff1-ce00-000000000000")
              {
                 Remove-CsPartnerApplication microsoft.sharepoint
      
                 New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx -ApplicationTrustLevel Full 
               }
            else
               {
                 Set-CsPartnerApplication -Identity microsoft.sharepoint -ApplicationTrustLevel Full 
                }
       }
    
    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

Speichern Sie das kopierte Skript dann mit der Dateierweiterung ".PS1" (z. B. unter "C:\\Scripts\\ServerToServerAuth.ps1"). Beachten Sie, dass Sie vor dem Ausführen des Skripts die metadata-URLs "https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1" und "http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx" durch die von Ihrem Exchange 2013- bzw. SharePoint-Server verwendeten metadata-URLs ersetzen müssen. Woran Sie die metadata-URL des jeweiligen Produkts erkennen, wird in der Produktdokumentation für Exchange 2013 und SharePoint beschrieben.

In der letzten Zeile des Skripts werden Sie bemerken, dass dort ein Set-CsOAuthConfiguration-Cmdlet mit der folgenden Syntax aufgerufen wird:

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

Da beim Aufruf des Set-CsOAuthConfiguration-Cmdlet der Realm-Parameter nicht verwendet wurde, wird als Bereich automatisch der FQDN (Fully Qualified Domain Name) Ihrer Organisation festgelegt (z. B. litwareinc.com). Wenn der Bereichsname anders als Ihr Organisationsname lautet, sollten Sie den Bereichsnamen wie folgt mit angeben:

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"

Nach diesen Änderungen können Sie das Skript ausführen und sowohl Exchange 2013 als auch SharePoint als Partneranwendungen konfigurieren. Führen Sie dazu das Skript in der Verwaltungsshell für Lync Server 2013 aus. Beispiel:

    C:\Scripts\ServerToServerAuth.ps1

Hinweis: Sie können das Skript auch dann ausführen, wenn Sie Exchange 2013 und SharePoint Server nicht installiert haben. Es sollten keine Probleme auftreten, wenn Sie zum Beispiel SharePoint Server als Partneranwendung konfigurieren, obwohl SharePoint Server bei Ihnen nicht installiert ist.

Bei Ausführung des Skripts würden Sie dann eine Fehlermeldung erhalten, die wie folgt aussieht:

    New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."

Diese Fehlermeldung hat meist zwei Bedeutungen: 1.) Eine der im Skript angegebenen URLs ist ungültig (d. h. eine Ihrer metadata-URLs ist keine echte metadata-URL); oder 2.) Eine der metadata-URLs konnte nicht kontaktiert werden. In diesem Fall sollten Sie überprüfen, ob die URLs korrekt geschrieben und zugreifbar sind, und Sie sollten das Skript danach erneut ausführen.

Nach dem Erstellen der Partneranwendung für Lync Server 2013 müssen Sie Lync Server als Partneranwendung für Exchange 2013 konfigurieren. Partneranwendungen für Exchange 2013 können Sie erstellen, indem Sie das Skript "Configure-EnterprisePartnerApplication" ausführen.1; dazu brauchen Sie nur die metadata-URL für Lync Server angeben und anzeigen, dass Lync Server die neue Partneranwendung ist.

Öffnen Sie zum Konfigurieren von Lync Server als Partneranwendung für Exchange die Exchange-Verwaltungsshell, und führen Sie einen Befehl ähnlich dem Folgenden aus:

    "c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://lync.contoso.com/metadata/json/1" -ApplicationType "Lync"

