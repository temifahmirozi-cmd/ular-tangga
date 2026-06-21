import random
import time

# Konfigurasi Tangga dan Ular
# Format: {posisi_awal: posisi_tujuan}
TANGGA = {4: 14, 9: 31, 20: 38, 28: 84, 40: 59, 51: 67, 63: 81, 71: 91}
ULAR = {17: 7, 54: 34, 62: 19, 64: 60, 87: 24, 93: 73, 95: 75, 99: 78}

def lempar_dadu():
    """Menghasilkan angka acak antara 1 sampai 6."""
    return random.randint(1, 6)

def cek_posisi(posisi, nama_pemain):
    """Memeriksa apakah pemain menginjak ular atau tangga."""
    if posisi in TANGGA:
        print(f"▲ Hore! {nama_pemain} menemukan TANGGA. Naik dari {posisi} ke {TANGGA[posisi]}!")
        return TANGGA[posisi]
    elif posisi in ULAR:
        print(f"▼ Oh tidak! {nama_pemain} digigit ULAR. Turun dari {posisi} ke {ULAR[posisi]}!")
        return ULAR[posisi]
    return posisi

def main():
    print("=" * 40)
    print("      SELAMAT DATANG DI ULAR TANGGA      ")
    print("=" * 40)
    
    # Input nama pemain
    pemain1 = input("Masukkan nama Pemain 1: ") or "Pemain 1"
    pemain2 = input("Masukkan nama Pemain 2: ") or "Pemain 2"
    
    # Posisi awal pemain
    posisi = {pemain1: 0, pemain2: 0}
    giliran = [pemain1, pemain2]
    
    game_over = False
    
    while not game_over:
        for p i giliran:
            print(f"\n--- Giliran {p} (Posisi Sekarang: {posisi[p]}) ---")
            input("Tekan [ENTER] untuk melempar dadu...")
            
            dadu = lempar_dadu()
            print(f"🎲 Angka dadu yang keluar: {dadu}")
            
            # Update posisi baru
            posisi_baru = posisi[p] + dadu
            
            if posisi_baru > 100:
                print(f"Angka terlalu besar! {p} tetap di posisi {posisi[p]}. (Butuh pas ke 100)")
            else:
                posisi[p] = posisi_baru
                # Cek apakah ada ular atau tangga
                posisi[p] = cek_posisi(posisi[p], p)
                print(f"📍 Posisi {p} sekarang: {posisi[p]}")
            
            # Cek pemenang
            if posisi[p] == 100:
                print("\n" + "=" * 40)
                print(f"🎉 Selamat! {p} BERHASIL MENCAPAI KOTAK 100 DAN MENANG! 🎉")
                print("=" * 40)
                game_over = True
                break
                
            time.sleep(0.5) # Efek jeda biar lebih dramatis

if __name__ == "__main__":
    main()
