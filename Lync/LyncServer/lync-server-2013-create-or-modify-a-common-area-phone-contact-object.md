---
title: Erstellen oder Ändern eines Kontaktobjekts für Telefone in öffentlichen Bereichen
TOCTitle: Erstellen oder Ändern eines Kontaktobjekts für Telefone in öffentlichen Bereichen
ms:assetid: eec33ad1-e4f2-49b2-91d6-d5a9d2e1714b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ994083(v=OCS.15)
ms:contentKeyID: 52056489
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen oder Ändern eines Kontaktobjekts für Telefone in öffentlichen Bereichen

 

_**Letztes Änderungsdatum des Themas:** 2013-02-20_

Sie verwenden das **New-CsCommonAreaPhone**-Cmdlet, um Active Directory-Domänendienste-Kontaktobjekte für alle Telefone im öffentlichen Bereich zu erstellen. Mit diesem Cmdlet können Sie entweder neue Kontaktobjekte für Telefone im öffentlichen Bereich erstellen oder vorhandene Kontaktobjekte mit Telefonen im öffentlichen Bereich verknüpfen. Zum Ändern der Eigenschaften der Kontaktobjekte, die mit Telefonen im öffentlichen Bereich verknüpft sind, verwenden Sie das **Set-CsCommonAreaPhone**-Cmdlet. Mit den optionalen Parameter für **Set-CsCommonAreaPhone** können Sie Objekte ändern, z. B. den Active Directory-Anzeigenamen des Kontakts oder den mit dem Telefon verknüpften Anschluss-URIs (Uniform Resource Identifier), und das Konto für die Verwendung mit Lync Server aktivieren oder deaktivieren. Informationen zu den möglichen Änderungen finden Sie im Abschnitt "Parameter" unter [Set-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCommonAreaPhone). Informationen zu **New-CsCommonAreaPhone**-Parametern finden Sie unter [New-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCommonAreaPhone).

Sie können diese beiden Cmdlets entweder in der Verwaltungsshell für Lync Server 2013 oder in einer Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).


## Erstellen eines Kontaktobjekts für Telefone im öffentlichen Bereich

  - Zum Erstellen eines neuen Kontaktobjekts für Telefone im öffentlichen Bereich verwenden Sie das **New-CsCommonAreaPhone**-Cmdlet. Beim Erstellen eines neuen Kontaktobjekts müssen Sie mindestens die folgenden Informationen angeben:
    
      - **LineUri**: Die Telefonnummer, die dem Telefon im öffentlichen Bereich zugeordnet ist. Beachten Sie, dass Sie die Telefonnummer im E.164-Format angeben müssen.
    
      - **RegistrarPool**: Der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Registrierungsstellenpools, in dem das Kontaktobjekt gehostet wird.
    
      - **OU**: Distinguished Name (DN) des Active Directory-Containers, in dem das Kontaktobjekt erstellt wird.
    
    Zudem wird empfohlen, einen Active Directory-Domänendienste-Anzeigenamen bereitzustellen. Andernfalls müssen Sie einen GUID verwenden, um die Telefonidentität anzugeben. Beispiel:
    
        New-CsCommonAreaPhone -LineUri "tel:+12065551219" -RegistrarPool "atl-cs-001.litwareinc.com" -OU "OU=Phones,dc=litwareinc,dc=com" -DisplayName "Lobby"

## Ändern eines Kontaktobjekts für Telefone im öffentlichen Bereich

  - Verwenden Sie das **Set-CsCommonAreaPhone**-Cmdlet, um die Eigenschaften eines vorhandenen Telefons im öffentlichen Bereich zu ändern. Mit diesem Befehl wird beispielsweise die SIP-Adresse für das Telefon im öffentlichen Bereich mit dem Anzeigennamen "Lobby" konfiguriert:
    
        Set-CsCommonAreaPhone -Identity "Lobby" -SipAddress "sip:lobby@litwareinc.com"

Einzelheiten dazu finden Sie in den Hilfethemen zu den Cmdlets [New-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCommonAreaPhone) und [Set-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCommonAreaPhone).

