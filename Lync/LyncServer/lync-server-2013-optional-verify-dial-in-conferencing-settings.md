---
title: 'Lync Server 2013: (Optional) Überprüfen der Einwahlkonferenzeinstellungen '
TOCTitle: '(Optional) Überprüfen der Einwahlkonferenzeinstellungen '
ms:assetid: a85efdda-97b0-4f3b-bd26-04416bee8ef5
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412789(v=OCS.15)
ms:contentKeyID: 49295018
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# (Optional) Überprüfen der Einwahlkonferenzeinstellungen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2010-11-02_

Zur endgültigen Bestätigung der Einwahlkonferenzkonfiguration können Sie nach Wähleinstellungen suchen, die eine Region für Einwahlkonferenzen aufweisen, die von keiner Zugriffsnummer verwendet wird, und nach Zugriffsnummern suchen, für die keine Region für Einwahlkonferenzen angegeben ist. Dieser Schritt ist optional.

## So ermitteln Sie Sätze mit Wähleinstellungen mit einer Region für Einwahlkonferenzen, die von keiner Zugriffsnummer verwendet wird

1.  Melden Sie sich beim Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle **Cs-ServerAdministrator** oder **CsAdministrator** an.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:
    
        Get-CsDialinConferencingAccessNumber -EmptyRegion
    
    Dieses Cmdlet gibt alle Sätze mit Wähleinstellungen mit einer Region für Einwahlkonferenzen zurück, die von keiner Zugriffsnummer verwendet wird.

## So bestimmen Sie Zugriffsnummern ohne zugewiesene Regionen

1.  Melden Sie sich beim Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle **Cs-ServerAdministrator** oder **CsAdministrator** an.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:
    
        Get-CsDialinConferencingAccessNumber -Region NULL
    
    Dieses Cmdlet gibt alle Zugriffsnummern für Einwahlkonferenzen zurück, die keiner Region zugeordnet sind.

