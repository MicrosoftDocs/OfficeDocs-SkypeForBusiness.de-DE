---
title: 'Lync Server 2013: Aushandlungseinstellungen für XMPP-Verbundpartner'
TOCTitle: Aushandlungseinstellungen für XMPP-Verbundpartner
ms:assetid: ef773942-ef92-4f71-85a1-738dfebdfa00
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ552456(v=OCS.15)
ms:contentKeyID: 49295835
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aushandlungseinstellungen für XMPP-Verbundpartner in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die Einstellungen für die Aushandlungstypen in der Konfiguration eines XMPP-Partners können die unterschiedlichsten Kombinationen annehmen. Doch nicht alle diese Kombinationen sind gültig. In der Tabelle in diesem Abschnitt werden die gültigen und die ungültigen Einstellungen beschrieben. Gängige Konfigurationen sind in der ersten Tabelle enthalten, die zweite Tabelle ist eine Auflistung aller möglichen Kombinationen. Beachten Sie, dass Sie *Simple Authentication and Security Layer* (SASL) **nur dann** verwenden können, wenn auch *Transport Layer Security* (TLS) verfügbar ist. SASL wird in einem unverschlüsselten (lesbaren) Format gesendet und sollte nie übertragen werden, es sei denn, es besteht Schutz durch einen anderen Mechanismus wie etwa TLS.

### Gängige XMPP-Partnerverbund-Aushandlungsmethoden

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Transport Layer Security (TLS)</th>
<th>Simple Authentication and Security Layer (SASL)</th>
<th>Rückrufauthentifizierung</th>
<th>Erwartete Authentifizierungsmethode(n)</th>
<th>Hinweise</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Erforderlich</p></td>
<td><p>Erforderlich</p></td>
<td><p>False</p></td>
<td><p>SASL über TLS</p></td>
<td><p>Wenn TLS und SASL auf <strong>Erforderlich</strong> festgelegt werden, kann damit sichergestellt werden, dass der SASL-Nachrichtenstream sicher ist. Rückruf ist nicht verfügbar und kann nicht für eine Fallbackmethode verwendet werden, wenn für den XMPP-Verbundpartner TLS nicht auf <strong>Erforderlich</strong> oder <strong>Optional</strong> festgelegt ist.</p></td>
</tr>
<tr class="even">
<td><p>Erforderlich</p></td>
<td><p>Optional</p></td>
<td><p>True</p></td>
<td><p>SASL über TLS, TLS-Rückruf, TCP-Rückruf</p></td>
<td><p>Wenn TLS auf <strong>Erforderlich</strong> festgelegt wird, wird SASL verwendet, wenn für den XMPP-Verbundpartner SASL auf <strong>Optional</strong> oder <strong>Erforderlich</strong> festgelegt ist. Ist SASL nicht verfügbar, wird Rückruf über TLS verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Optional</p></td>
<td><p>Optional</p></td>
<td><p>True</p></td>
<td><p>SASL über TLS, TLS-Rückruf, TCP-Rückruf</p></td>
<td><p>Diese Einstellungen sind zwar sehr flexibel hinsichtlich der angebotenen Aushandlungsmethoden, erfordern aber die Einstellungen des XMPP-Verbundpartners. Wenn für den Partner TLS auf <strong>Optional</strong> oder <strong>Erforderlich</strong> festgelegt ist, SASL aber nicht unterstützt wird, ist TLS-Rückruf verfügbar. Wenn für den Partner TLS und SASL auf <strong>Optional</strong> oder <strong>Erforderlich</strong> festgelegt sind, wird die optimale Auswahl von TLS über SASL verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Nicht unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>True</p></td>
<td><p>TCP-Rückruf</p></td>
<td><p>In vielen Fällen ist TCP-Rückruf die einzig mögliche Lösung. Das ist zwar weniger optimal als andere Optionen, bietet aber ein bestimmtes Maß an Vertrauenswürdigkeit.</p></td>
</tr>
</tbody>
</table>


### Schema der XMPP-Partnerverbund-Aushandlungsmethoden (vollständig)

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Transport Layer Security (TLS)</th>
<th>Simple Authentication and Security Layer (SASL)</th>
<th>Rückrufauthentifizierung</th>
<th>Erwartete Authentifizierungsmethode</th>
<th>Anmerkungen, Warnung oder Fehler wegen ungültiger Konfiguration</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Erforderlich</p></td>
<td><p>Erforderlich</p></td>
<td><p>True</p></td>
<td><p>SASL über TLS</p></td>
<td><div>

> [!WARNING]
> Rückruf funktioniert nicht, wenn sowohl SASL als auch TLS erforderlich ist.


</div></td>
</tr>
<tr class="even">
<td><p>Erforderlich</p></td>
<td><p>Erforderlich</p></td>
<td><p>False</p></td>
<td><p>SASL über TLS</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Optional</p></td>
<td><p>Erforderlich</p></td>
<td><p>True</p></td>
<td><p>SASL über TLS, TLS-Rückruf, TCP-Rückruf</p></td>
<td><div>

> [!WARNING]
> SASL erfordert TLS. Wenn TLS optional sein darf, kann dies zu Fehlern bei Sitzungsaushandlungen führen.


</div></td>
</tr>
<tr class="even">
<td><p>Optional</p></td>
<td><p>Erforderlich</p></td>
<td><p>False</p></td>
<td><p>SASL über TLS</p></td>
<td><div>

> [!WARNING]
> SASL erfordert TLS. Wenn TLS optional sein darf, kann dies zu Fehlern bei Sitzungsaushandlungen führen.


</div></td>
</tr>
<tr class="odd">
<td><p>Nicht unterstützt</p></td>
<td><p>Erforderlich</p></td>
<td><p>True</p></td>
<td><p>TCP-Rückruf</p></td>
<td><div>

> [!WARNING]
> SASL erfordert TLS. Wenn TLS optional sein darf, kann dies zu Fehlern bei Sitzungsaushandlungen führen.


</div></td>
</tr>
<tr class="even">
<td><p>Nicht unterstützt</p></td>
<td><p>Erforderlich</p></td>
<td><p>False</p></td>
<td><div>

> [!WARNING]
> Ungültige Konfiguration


</div></td>
<td><div>

> [!WARNING]
> Da SASL TLS erfordert und TLS nicht verfügbar ist, SASL/TLS kann nicht erfolgreich sein. TCP-Rückruf ist auf <STRONG>False</STRONG> festgelegt und kann nicht verwendet werden.


</div></td>
</tr>
<tr class="odd">
<td><p>Erforderlich</p></td>
<td><p>Optional</p></td>
<td><p>True</p></td>
<td><p>SASL über TLS, TLS-Rückruf</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Erforderlich</p></td>
<td><p>Optional</p></td>
<td><p>False</p></td>
<td><p>SASL über TLS</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Optional</p></td>
<td><p>Optional</p></td>
<td><p>True</p></td>
<td><p>SASL über TLS, TLS-Rückruf, TCP-Rückruf</p></td>
<td><div>

> [!WARNING]
> SASL erfordert TLS. Wenn TLS optional sein darf, kann dies zu Fehlern bei Sitzungsaushandlungen führen.


</div></td>
</tr>
<tr class="even">
<td><p>Optional</p></td>
<td><p>Optional</p></td>
<td><p>False</p></td>
<td><p>SASL über TLS</p></td>
<td><div>

> [!WARNING]
> SASL erfordert TLS. Wenn TLS optional sein darf, kann dies zu Fehlern bei Sitzungsaushandlungen führen.


</div></td>
</tr>
<tr class="odd">
<td><p>Nicht unterstützt</p></td>
<td><p>Optional</p></td>
<td><p>True</p></td>
<td><p>TCP-Rückruf</p></td>
<td><div>

> [!WARNING]
> SASL erfordert TLS. Wenn TLS optional sein darf, kann dies zu Fehlern bei Sitzungsaushandlungen führen.


</div></td>
</tr>
<tr class="even">
<td><p>Nicht unterstützt</p></td>
<td><p>Optional</p></td>
<td><p>False</p></td>
<td><div>

> [!WARNING]
> Ungültige Konfiguration


</div></td>
<td><div>

> [!WARNING]
> SASL erfordert TLS. Wenn TLS optional sein darf, kann dies zu Fehlern bei Sitzungsaushandlungen führen.


</div></td>
</tr>
<tr class="odd">
<td><p>Erforderlich</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>True</p></td>
<td><p>TLS-Rückruf</p></td>
<td><p>Konfiguration erlaubt TLS-Rückruf.</p></td>
</tr>
<tr class="even">
<td><p>Erforderlich</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>False</p></td>
<td><p>Ungültige Konfiguration</p></td>
<td><div>

> [!WARNING]
> SASL oder Rückruf muss aktiviert sein.


</div></td>
</tr>
<tr class="odd">
<td><p>Optional</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>True</p></td>
<td><p>TLS-Rückruf, TCP-Rückruf</p></td>
<td><p>Je nach den Aushandlungsoptionen am anderen Endpunkt wird TCP- oder TLS-Rückruf akzeptiert.</p></td>
</tr>
<tr class="even">
<td><p>Optional</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>False</p></td>
<td><p>Ungültige Konfiguration</p></td>
<td><div>

> [!WARNING]
> SASL oder Rückruf muss aktiviert sein.


</div></td>
</tr>
<tr class="odd">
<td><p>Nicht unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>True</p></td>
<td><p>TCP-Rückruf</p></td>
<td><p>TCP-Rückruf ist die einzige verfügbare Aushandlungsmethode</p></td>
</tr>
<tr class="even">
<td><p>Nicht unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>False</p></td>
<td><p>Ungültige Konfiguration</p></td>
<td><div>

> [!WARNING]
> SASL oder Rückruf muss aktiviert sein.


</div></td>
</tr>
</tbody>
</table>

