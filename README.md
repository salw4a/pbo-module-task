using System;
using System.Runtime.CompilerServices;

public class Hewan
{
    public string Name { get; set; }
    public int Age { get; set; }

    protected Hewan(string name, int age)
    {
        Name = name;
        Age = age;
    }

    public virtual void InfoHewan()
    {
        Console.WriteLine($"Nama : {Name}");
        Console.WriteLine($"Umur : {Age}");
    }

    public virtual string Suara()
    {
        return "Hewan ini bersuara";
    }
}

public class Mamalia : Hewan
{
    public int jumlahKaki {get; set;}
    public Mamalia(string  name, int age, int feettotal) : base(name, age)
    {
        jumlahKaki = feettotal;
    }

    public override void InfoHewan()
    {
        base.InfoHewan();
        Console.WriteLine($"Jumlah kaki : {jumlahKaki}");
    }
    public override string Suara()
    {
        return base.Suara();
    }
}

public class Reptil : Hewan
{
    public int PanjangTubuh { get; set; }
    public Reptil(string name, int age, double panjangTubuh) : base(name, age)
    {
        PanjangTubuh = PanjangTubuh;
    }
    public override void InfoHewan()
    {
        base.InfoHewan();
        Console.WriteLine($"Panjang tubuh : {PanjangTubuh}");
    }
    public override string Suara()
    {
        return base.Suara();
    }
}

public class Singa : Mamalia
{
    public Singa(string name, int age) : base(name, age, 4) { }

    public override void InfoHewan()
    {
        base.InfoHewan();
    }
    public void Mengaum()
    {
        Console.WriteLine($"{Name} mengaum dengan keras");
    }
    public override string Suara()
    {
        return ($"{Name}  suaranya Rraawrrrr");
    }
}
public class Gajah : Mamalia
{
    public Gajah(string name, int age) : base(name, age, 4) { }

    public override void InfoHewan()
    {
        base.InfoHewan();
    }
    public override string Suara()
    {
        return($"{Name} suaranya Pprrrrr");
    }
}

public class Ular : Reptil
{
    public Ular(string name, int age, int panjangTubuh) : base(name, age, panjangTubuh) { }

    public override void InfoHewan()
    {
        base.InfoHewan();
    }
    public void Merayap()
    {
        Console.WriteLine("Ular merayap dengan pelan atau cepat");
    }
    public override string Suara()
    {
        return ($"{Name} suaranya Sheesshhh");
    }
}

public class Buaya : Reptil
{
    public Buaya(string name, int age, int panjangTubuh) : base(name, age, panjangTubuh) { }
    public override void InfoHewan()
    {
        base.InfoHewan();
    }
    public override string Suara()
    {
        return ($"{Name} suaranya Ggrrrrrr");
    }
}
public class KebunBinatang
{
    private List<Hewan> koleksiHewan = new List<Hewan>();
    public void TambahHewan(Hewan hewan)
    {
        koleksiHewan.Add(hewan);
        Console.WriteLine($"{hewan.Name} telah ditambahkan ke dalam kebun binatang sukacita!");
        Console.WriteLine("=============================================================");

    }
    public void DaftarHewan()
    {
        Console.WriteLine("====== Daftar Hewan ======");
        foreach (var hewan in koleksiHewan)
        {
            hewan.InfoHewan();
            Console.WriteLine();
        }
    }
}

public class Program
{
    static void Main(string[] args)
    {
        KebunBinatang kebunBinatang = new KebunBinatang();
        Singa singa1 = new Singa("Panthera", 9);
        Singa singa2 = new Singa("Leo", 3);
        Singa singa3 = new Singa("Simba", 1);
        Singa singa4 = new Singa("Kahleo", 6);
        Gajah gajah1 = new Gajah("Maximus", 3);
        Gajah gajah2 = new Gajah("Ganesha", 5);
        Gajah gajah3 = new Gajah("Loxo", 4);
        Gajah gajah4 = new Gajah("Donta", 1);
        Ular ular1 = new Ular("Kobra", 1, 10);
        Ular ular2 = new Ular("Anakonda", 4, 28);
        Ular ular3 = new Ular("Mamba", 6, 18);
        Ular ular4 = new Ular("Draco", 3, 34);
        Buaya buaya1 = new Buaya("Alligator", 3, 120);
        Buaya buaya2 = new Buaya("Catman", 6, 250);
        Buaya buaya3 = new Buaya("Nile", 2, 112);
        Buaya buaya4 = new Buaya("Cuban", 1, 96);


        kebunBinatang.TambahHewan(singa1);
        kebunBinatang.TambahHewan(singa2);
        kebunBinatang.TambahHewan(singa3);
        kebunBinatang.TambahHewan(singa4);
        kebunBinatang.TambahHewan(gajah1);
        kebunBinatang.TambahHewan(gajah2);
        kebunBinatang.TambahHewan(gajah3);
        kebunBinatang.TambahHewan(gajah4);
        kebunBinatang.TambahHewan(ular1);
        kebunBinatang.TambahHewan(ular2);
        kebunBinatang.TambahHewan(ular3);
        kebunBinatang.TambahHewan(ular4);
        kebunBinatang.TambahHewan(buaya1);
        kebunBinatang.TambahHewan(buaya2);
        kebunBinatang.TambahHewan(buaya3);
        kebunBinatang.TambahHewan(buaya4);

        Console.WriteLine();
        kebunBinatang.DaftarHewan();
        Console.WriteLine();

        Console.WriteLine(singa1.Suara()); 
        Console.WriteLine(singa3.Suara());
        Console.WriteLine(gajah2.Suara());
        Console.WriteLine(gajah4.Suara());
        Console.WriteLine(ular3.Suara());
        Console.WriteLine(ular4.Suara());
        Console.WriteLine(buaya1.Suara());
        Console.WriteLine(buaya2.Suara());
        Console.WriteLine();

        singa2.Mengaum();
        singa4.Mengaum();

        Console.WriteLine(gajah3.Suara());
        Console.WriteLine();
        Console.WriteLine(ular1.Suara());
        Console.WriteLine();
        singa1.Mengaum();
        Console.WriteLine();
        singa1.InfoHewan();
        Console.WriteLine();
        ular4.Merayap();
        Console.WriteLine();

        Reptil reptil = new Buaya("Caiman", 3, 138);
        Console.WriteLine(reptil.Suara());
    }
}
