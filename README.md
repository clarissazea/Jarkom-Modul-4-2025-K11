# Jarkom-Modul-4-2025-K11

# CIDR (CPT)

## Tabel Alokasi Subnet

| Nama Subnet | Rute | Jumlah IP | Jumlah host + gateway | Netmask |
|-------------|------|------------|------------------------|---------|
| A1 | Valinor > Switch > Shadow > Switch > Anarion > Switch > Lindon | 298 | 299 | /23 |
| A2 | Valmar > Switch > Doriath > Switch > Arnor | 27 | 28 | /27 |
| A3 | Valmar > Switch > Imrahil > Switch > Utumno > Switch > Gwaith | 33 | 34 | /26 |
| A4 | Fornost > Switch > Valinor > Switch > Valmar | 3 | 3 | /29 |
| A5 | Amonsul > Fornost | 2 | 2 | /30 |
| A6 | Eregion > Switch > Mirkwood > Switch > Morgul | 125 | 126 | /25 |
| A7 | Gudur > Switch > Palantir > Switch > Edhil | 119 | 120 | /25 |
| A8 | Gudur > Switch > IronCrown > Switch > Grond > Switch > Hobbiton | 13 | 14 | /28 |
| A9 | Numenor > Switch > Arthedain > Switch > Mirdain | 874 | 875 | /22 |
| A10 | Erain > Switch > Melkor > Switch > Khazad | 502 | 503 | /23 |
| A11 | Erain > Switch > Balrog > Switch > Gothmog > Switch > Thrandul | 469 | 470 | /23 |
| A12 | Mordor > Erain | 2 | 2 | /30 |
| A13 | Numenor > Mordor | 2 | 2 | /30 |
| A14 | Gudur > Numenor | 2 | 2 | /30 |
| A15 | Eregion > Numenor | 2 | 2 | /30 |
| A16 | Amonsul > Eregion | 2 | 2 | /30 |
| A17 | Amonsul > Minastir | 2 | 2 | /30 |
| A18 | Minastir > Amroth | 2 | 2 | /30 |
| A19 | Amroth > Switch > Morgoth > Switch > Throne | 3 | 3 | /29 |
| A20 | Morgoth > Switch > Erendis > Switch > Elrond | 61 | 62 | /26 |
| A21 | Throne > Erebor | 2 | 3 | /29 |
| A22 | Anor > Switch > Silmarils > Switch > Beacon | 660 | 661 | /22 |
| A23 | Minastir > Anor | 2 | 2 | /30 |
| **Total** | — | **3207** | **3219** | **/20** |

## Topologi

<img width="1589" height="919" alt="cidr fix" src="https://github.com/user-attachments/assets/30d87e46-631e-418c-98b5-29bc22c2b091" />

## Penggabungan

### Langkah 1

<img width="1589" height="919" alt="CIDR A" src="https://github.com/user-attachments/assets/3ab40773-5f55-436a-9e38-0fd2f5a340b6" />

## Langkah 2
<img width="1589" height="919" alt="CIDR B" src="https://github.com/user-attachments/assets/630eb698-e795-47dc-ba0a-49b574f153bc" />

### Tabel Gabungan Subnet – Level B

| Subnet | Gabungan dari 1 | Netmask | Gabungan dari 2 | Netmask | Netmask Akhir |
|--------|------------------|---------|------------------|---------|----------------|
| B1     | A1               | /23     | A4               | /29     | /22            |
| B2     | A2               | /27     | A3               | /26     | /25            |
| B3     | A7               | /25     | A8               | /28     | /24            |
| B4     | A10              | /24     | A11              | /23     | /22            |
| B5     | A22              | /22     | A23              | /30     | /21            |
| B6     | A19              | /29     | A20              | /26     | /25            |



## Langkah 3
<img width="1589" height="919" alt="CIDR C" src="https://github.com/user-attachments/assets/8e448865-da16-434c-91bd-20e361db4355" />

### Tabel Gabungan Subnet – Level C

| Subnet | Gabungan dari 1 | Netmask | Gabungan dari 2 | Netmask | Netmask Akhir |
|--------|------------------|---------|------------------|---------|----------------|
| C1     | B1               | /22     | B2               | /25     | /21            |
| C2     | B3               | /24     | A14              | /30     | /23            |
| C3     | B4               | /22     | A12              | /30     | /21            |
| C4     | B6               | /25     | A21              | /29     | /24            |


## Langkah 4
<img width="1589" height="919" alt="CIDR D" src="https://github.com/user-attachments/assets/c13e07ef-818a-4290-bfa4-7e4ce86a0adf" />

### Tabel Gabungan Subnet – Level D

| Subnet | Gabungan dari 1 | Netmask | Gabungan dari 2 | Netmask | Netmask Akhir |
|--------|------------------|---------|------------------|---------|----------------|
| D1     | C1               | /21     | A5               | /30     | /20            |
| D2     | C2               | /23     | A9               | /22     | /21            |
| D3     | C3               | /21     | A13              | /30     | /20            |
| D4     | C4               | /24     | A18              | /30     | /23            |



## Langkah 5
<img width="1589" height="919" alt="E FIX" src="https://github.com/user-attachments/assets/4f9d138b-5505-479b-8068-7129f161a3d3" />

### Tabel Gabungan Subnet – Level E


| Subnet | Gabungan dari 1 | Netmask | Gabungan dari 2 | Netmask | Netmask Akhir |
|--------|------------------|---------|------------------|---------|----------------|
| E1     | D4               | /23     | B5               | /21     | /20            |
| E2     | D2               | /21     | D3               | /20     | /19            |


## Langkah 6
<img width="1589" height="919" alt="F FIX" src="https://github.com/user-attachments/assets/61790787-07b9-497f-8efe-e3b78922b638" />

### Tabel Gabungan Subnet – Level F

| Subnet | Gabungan dari 1 | Netmask | Gabungan dari 2 | Netmask | Netmask Akhir |
|--------|------------------|---------|------------------|---------|----------------|
| F1     | E2               | /19     | A15              | /30     | /18            |


## Langkah 7
<img width="1589" height="919" alt="CIDR G" src="https://github.com/user-attachments/assets/513e3df9-2256-4217-847d-00e863a9f4f4" />

### Tabel Gabungan Subnet – Level G

| Subnet | Gabungan dari 1 | Netmask | Gabungan dari 2 | Netmask | Netmask Akhir |
|--------|------------------|---------|------------------|---------|----------------|
| G1     | F1               | /20     | A6               | /25     | /19            |


## Langkah 8
<img width="1589" height="919" alt="CIDR H" src="https://github.com/user-attachments/assets/86badeff-31e9-4580-a5b7-b721ef084aa2" />

### Tabel Gabungan Subnet – Level H

| Subnet | Gabungan dari 1 | Netmask | Gabungan dari 2 | Netmask | Netmask Akhir |
|--------|------------------|---------|------------------|---------|----------------|
| H1     | G1               | /19     | A16              | /30     | /18            |
| H2     | E1               | /20     | A17              | /30     | /19            |



## Langkah 9
<img width="1676" height="943" alt="CIDR I" src="https://github.com/user-attachments/assets/bdc1e7e3-bb19-410d-82a0-42446ecdf12d" />

### Tabel Gabungan Subnet – Level I

| Subnet | Gabungan dari 1 | Netmask | Gabungan dari 2 | Netmask | Netmask Akhir |
|--------|------------------|---------|------------------|---------|----------------|
| I1     | H1               | /18     | H2               | /19     | /17            |


## Langkah 10
<img width="1676" height="943" alt="CIDR J" src="https://github.com/user-attachments/assets/619afe21-e6ac-47f3-88dc-55f4a7cc71e1" />

### Tabel Gabungan Subnet – Level J

| Subnet | Gabungan dari 1 | Netmask | Gabungan dari 2 | Netmask | Netmask Akhir |
|--------|------------------|---------|------------------|---------|----------------|
| J1     | I1               | /17     | D1               | /20     | /16            |



## Tree CIDR

<img width="1561" height="746" alt="image" src="https://github.com/user-attachments/assets/a58adbab-934c-472d-87a4-a79ecc8b9371" />


## Tabel Pembagian Subnet

### Prefix IP: 10.69

| Subnet | CIDR     | Netmask        | IP Range              | Jumlah IP | Keterangan        |
|--------|----------|----------------|------------------------|-----------|-------------------|
| A      | 192.168.1.0/24  | 255.255.255.0  | 192.168.1.0 – 192.168.1.255  | 256       | Subnet utama      |
| B      | 192.168.1.0/26  | 255.255.255.192| 192.168.1.0 – 192.168.1.63   | 64        | Subnet kecil 1    |
| C      | 192.168.1.64/26 | 255.255.255.192| 192.168.1.64 – 192.168.1.127 | 64        | Subnet kecil 2    |
| D      | 192.168.1.128/27| 255.255.255.224| 192.168.1.128 – 192.168.1.159| 32        | Subnet mikro 1    |
| E      | 192.168.1.160/27| 255.255.255.224| 192.168.1.160 – 192.168.1.191| 32        | Subnet mikro 2    |
| F      | 192.168.1.192/28| 255.255.255.240| 192.168.1.192 – 192.168.1.207| 16        | Subnet mini 1     |
| G      | 192.168.1.208/28| 255.255.255.240| 192.168.1.208 – 192.168.1.223| 16        | Subnet mini 2     |
| H      | 192.168.1.224/29| 255.255.255.248| 192.168.1.224 – 192.168.1.231| 8         | Subnet kecil sekali|
| I      | 192.168.1.232/30| 255.255.255.252| 192.168.1.232 – 192.168.1.235| 4         | Point-to-point    |
| J      | 192.168.1.236/30| 255.255.255.252| 192.168.1.236 – 192.168.1.239| 4         | Point-to-point    |

