---
title: Zuweisen einer Benutzerrichtlinie für gehostete Voicemail
TOCTitle: Zuweisen einer Benutzerrichtlinie für gehostete Voicemail
ms:assetid: d44c71a0-4407-4ab4-b7e0-d671dde3425f
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398919(v=OCS.15)
ms:contentKeyID: 49295515
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zuweisen einer Benutzerrichtlinie für gehostete Voicemail

 

_**Letztes Änderungsdatum des Themas:** 2010-11-07_

Die Bereitstellung einer oder mehrerer Benutzerrichtlinien für gehostete Voicemail ist optional. Wenn Sie Richtlinien auf Benutzerebene bereitstellen, müssen Sie diese Benutzern, Gruppen oder Kontaktobjekten explizit zuweisen.

Ausführliche Informationen zum Zuweisen von Richtlinien für gehostete Voicemail auf Benutzerebene und zum Entfernen von Zuweisungen finden Sie in der Lync Server-Verwaltungsshell-Dokumentation für die folgenden Cmdlets:

  - Grant-CsHostedVoicemailPolicy

  - Remove-CsHostedVoicemailPolicy

## So weisen Sie eine Benutzerrichtlinie für gehostete Voicemail zu

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet "Grant-CsHostedVoicemailPolicy" aus, um die Benutzerrichtlinie für gehostete Voicemail einzelnen Benutzern, Gruppen oder Kontaktobjekten zuzuweisen. Führen Sie beispielsweise den folgenden Befehl aus:
    
        Grant-CsHostedVoicemailPolicy -Identity "Ken Myer" -PolicyName ExRedmond
    
    In diesem Beispiel wird die Richtlinie für gehostete Voicemail "ExRedmond" dem Benutzer Ken Myer zugewiesen.
    
    **Identity** gibt die Identität des zu ändernden Benutzerkontos an. Der Wert "Identity" kann unter Verwendung eines der folgenden Formate angegeben werden:
    
      - SIP-Adresse des Benutzers
    
      - Active Directory-Benutzerprinzipalname des Benutzers
    
      - Domänenanmeldename des Benutzers (zum Beispiel "contoso\\kenmyer")
    
      - AD DS-Anzeigename des Benutzers (zum Beispiel "Ken Myer"). Wenn der Anzeigename als Identitätswert verwendet wird, können Sie das Sternchen (\*) als Platzhalterzeichen nutzen. Der Identitätswert "\* Smith" gibt beispielsweise alle Benutzer zurück, deren Anzeigename auf den Zeichenfolgenwert "Smith" endet.
    

    > [!NOTE]
    > Der Active Directory-SAM-Kontoname eines Benutzers kann nicht als Identitätswert verwendet werden, da dieser Name innerhalb der Gesamtstruktur nicht unbedingt eindeutig ist.


