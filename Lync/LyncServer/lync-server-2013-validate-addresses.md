---
title: Überprüfen von Adressen
TOCTitle: Überprüfen von Adressen
ms:assetid: aae557c9-e6f5-4d23-8af1-1d4cd7968c54
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412808(v=OCS.15)
ms:contentKeyID: 49295049
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Überprüfen von Adressen

 

_**Letztes Änderungsdatum des Themas:** 2012-09-17_

Vor der Veröffentlichung der Standortdatenbank müssen Sie neue Standorte im Abgleich mit der MSAG-Datenbank (Master Street Address Guide) validieren, die vom Dienstanbieter für SIP-Trunks oder Festnetzanschlüsse (Public Switched Telephone Network, PSTN) mit Notrufunterstützung verwaltet wird.

Einzelheiten zu Dienstanbietern für SIP-Trunks mit Notrufunterstützung finden Sie unter [Auswählen eines E9-1-1-Dienstanbieters für Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md).

Weitere Informationen zum Validieren von Adressen finden Sie in der Lync Server-Verwaltungsshell-Dokumentation der folgenden Cmdlets:

  - **Get-CsLisServiceProvider**

  - **Set-CsLisServiceProvider**

  - **Remove-CsLisServiceProvider**

  - **Get-CsLisCivicAddress**

  - **Test-CsLisCivicAddress**

## So überprüfen Sie Adressen in der Standortdatenbank auf Gültigkeit

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Führen Sie die folgenden Cmdlets zum Konfigurieren der Verbindung mit dem Anbieter für die Notrufunterstützung aus.
    
        $pwd = Read-Host -AsSecureString <password>
        Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd

3.  Führen das folgende Cmdlet zum Überprüfen der Gültigkeit von Adressen in der Standortdatenbank aus.
    
        Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
    
    Mit dem Cmdlet **Test-CsLisCivicAddress** können Sie auch einzelne Adressen validieren.

