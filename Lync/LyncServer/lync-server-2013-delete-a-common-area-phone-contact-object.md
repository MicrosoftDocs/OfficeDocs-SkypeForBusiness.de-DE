---
title: Löschen eines Kontaktobjekts für Telefone in öffentlichen Bereichen
TOCTitle: Löschen eines Kontaktobjekts für Telefone in öffentlichen Bereichen
ms:assetid: f4c139dc-f07c-4c75-9345-e291aea41173
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ994087(v=OCS.15)
ms:contentKeyID: 52056503
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Löschen eines Kontaktobjekts für Telefone in öffentlichen Bereichen

 

_**Letztes Änderungsdatum des Themas:** 2013-02-20_

Gelegentlich möchten Sie möglicherweise das Kontaktobjekt löschen, das einem Telefon im öffentlichen Bereich zugeordnet ist. Wenn Sie beispielsweise das Telefon aus einem Aufenthaltsraum für Mitarbeiter entfernen, muss diesem Telefon kein Kontaktobjekt mehr zugeordnet sein. Mit dem **Remove-CsCommonAreaPhone**-Cmdlet können Sie Konten für Telefone im öffentlichen Bereich löschen. Wenn Sie dieses Cmdlet ausführen, wird das Telefon aus der Liste der Telefone im öffentlichen Bereich gelöscht, die von **Get-CsCommonAreaPhone** zurückgegeben wird. Zusätzlich wird das dem jeweiligen Telefon zugeordnete Kontaktobjekt aus Active Directory-Domänendienste gelöscht.

Verwenden Sie das **Remove-CsCommonAreaPhone**-Cmdlet, um ein Telefon im öffentlichen Bereich bzw. alle Telefone im öffentlichen Bereich zu löschen, die ein gemeinsames Element haben, z. B. den Anzeigenamen oder das Land und die Vorwahl. Dieses Cmdlet kann entweder über die Verwaltungsshell für Lync Server 2013 oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).


## Entfernen eines angegebenen Telefons im öffentlichen Bereich

  - Mit dem folgenden Befehl wird das Telefon im öffentlichen Bereich mit der SIP-Adresse "sip:mainlobby@litwareinc.com" entfernt:
    
        Remove-CsCommonAreaPhone -Identity "sip:mainlobby@litwareinc.com"

## Entfernen eines Telefons im öffentlichen Bereich basierend auf dem Anzeigenamen

  - Mit diesem Befehl werden alle Telefone im öffentlichen Bereich entfernt, deren Anzeigename den Zeichenfolgenwert "Building 14" enthält:
    
        Get-CsCommonAreaPhone | Where-Object {$_.DisplayName -match "Building 14"} | Remove-CsCommonAreaPhone

## Entfernen eines Telefons im öffentlichen Bereich basierend auf dem Land und der Vorwahl

  - Mit diesem Befehl werden alle Telefone im öffentlichen Bereich für die USA (Ländercode 1) und die Ortsvorwahl 425 entfernt:
    
        Get-CsCommonAreaPhone | Where-Object {$_.LineUri  -match "^tel:\+1425"} | Remove-CsCommonAreaPhone

Einzelheiten dazu finden Sie im Hilfethema zum Cmdlet [Remove-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCommonAreaPhone).

## Siehe auch

#### Weitere Ressourcen

[Get-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCommonAreaPhone)

