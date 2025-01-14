// ignore_for_file: prefer_typing_uninitialized_variables, non_constant_identifier_names

import 'package:flutter/material.dart';


void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  // This widget is the root of your application.
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      theme: ThemeData(
        // This is the theme of your application.
        //
        // TRY THIS: Try running your application with "flutter run". You'll see
        // the application has a purple toolbar. Then, without quitting the app,
        // try changing the seedColor in the colorScheme below to Colors.green
        // and then invoke "hot reload" (save your changes or press the "hot
        // reload" button in a Flutter-supported IDE, or press "r" if you used
        // the command line to start the app).
        //
        // Notice that the counter didn't reset back to zero; the application
        // state is not lost during the reload. To reset the state, use hot
        // restart instead.
        //
        // This works for code too, not just values: Most code changes can be
        // tested with just a hot reload.
        colorScheme: ColorScheme.fromSeed(seedColor: Colors.deepPurple),
        useMaterial3: true,
      ),
      home: const MyHomePage(title: 'Flutter Home Page'),
    );
  }
}
class MyHomePage extends StatelessWidget {
  final String title;

  const MyHomePage({super.key, required this.title});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text(title),
      ),
      body: const Center(
        child: Text('Halo Flutter!'),
      ),
    );
  }
}

class ImageContainer extends StatelessWidget {
  const ImageContainer({super.key});

  @override
  Widget build(BuildContext context) {
    return Container(
      color: const Color.fromRGBO(116, 236, 52, 1),
      constraints: const BoxConstraints(maxWidth: 480),
      width: double.infinity,
      child: Padding(
        padding: const EdgeInsets.symmetric(vertical: 232),
        child: Center(
          child: AspectRatio(
            aspectRatio: 1.01,
            child: Image.network(
              'https://cdn.builder.io/api/v1/image/assets/TEMP/0a0ca5fb473edf53c8fa7eb742375edd0546241a608ed4f48086b10958c516b8?placeholderIfAbsent=true&apiKey=ecbae26a8caa46b68836fb14492d06ac',
              fit: BoxFit.contain,
              loadingBuilder: (context, child, loadingProgress) {
                if (loadingProgress == null) return child;
                return const Center(child: CircularProgressIndicator());
              },
              semanticLabel: 'Decorative image',
            ),
          ),
        ),
      ),
    );
  }
}




class LoginScreen extends StatelessWidget {
  const LoginScreen({super.key});

  @override
  Widget build(BuildContext context) {
    var GoogleFonts;
    return Scaffold(
      backgroundColor: const Color(0xFFF8F8F8),
      body: SingleChildScrollView(
        child: Padding(
          padding: const EdgeInsets.fromLTRB(31, 30, 10, 193),
          child: Center(
            child: Container(
              constraints: const BoxConstraints(maxWidth: 480),
              child: Column(
                crossAxisAlignment: CrossAxisAlignment.center,
                children: [
                  Align(
                    alignment: Alignment.centerRight,
                    child: Container(
                      padding: const EdgeInsets.symmetric(
                        horizontal: 23,
                        vertical: 12,
                      ),
                      decoration: BoxDecoration(
                        color: const Color(0xFF74EC34),
                        borderRadius: BorderRadius.circular(20),
                      ),
                      child: const Text(
                        'Register',
                        style: TextStyle(
                          fontSize: 20,
                          color: Colors.black,
                        ),
                      ),
                    ),
                  ),
                  const SizedBox(height: 18),
                  Image.network(
                    'https://cdn.builder.io/api/v1/image/assets/TEMP/632a3e821d8381ae538d6901bd64d8b5d6c93763a80fbbaf0deee94c53f3451a?placeholderIfAbsent=true&apiKey=ecbae26a8caa46b68836fb14492d06ac',
                    width: 213,
                    fit: BoxFit.contain,
                    semanticLabel: 'Welcome Image',
                  ),
                  const SizedBox(height: 21),
                  Text(
                    'Selamat datang di aplikasi kami!',
                    style: GoogleFonts.merriweatherSans(
                      fontSize: 20,
                      fontWeight: FontWeight.w800,
                      color: Colors.black,
                    ),
                  ),
                  Form(
                    child: Column(
                      crossAxisAlignment: CrossAxisAlignment.start,
                      children: [
                        const SizedBox(height: 49),
                        Padding(
                          padding: const EdgeInsets.only(left: 19),
                          child: Row(
                            children: [
                              Image.network(
                                'https://cdn.builder.io/api/v1/image/assets/TEMP/89f8aa1d0e7c0e3328412e09aa979ef516232ad3fc9bb6a4e949881c087dd1e8?placeholderIfAbsent=true&apiKey=ecbae26a8caa46b68836fb14492d06ac',
                                width: 43,
                                fit: BoxFit.contain,
                                semanticLabel: 'Email Icon',
                              ),
                              const SizedBox(width: 9),
                              Semantics(
                                label: 'Email or Username input field',
                                child: TextFormField(
                                  decoration: const InputDecoration(
                                    labelText: 'Email/Username',
                                    labelStyle: TextStyle(
                                      fontSize: 24,
                                      color: Color(0xFFB0A6A6),
                                    ),
                                  ),
                                ),
                              ),
                            ],
                          ),
                        ),
                        const SizedBox(height: 41),
                        Padding(
                          padding: const EdgeInsets.only(left: 26),
                          child: Row(
                            children: [
                              Image.network(
                                'https://cdn.builder.io/api/v1/image/assets/TEMP/d461a2a06fe49002d480837940aeb98a95570dbbc2d29c8549e073b61a9eb998?placeholderIfAbsent=true&apiKey=ecbae26a8caa46b68836fb14492d06ac',
                                width: 29,
                                fit: BoxFit.contain,
                                semanticLabel: 'Password Icon',
                              ),
                              const SizedBox(width: 16),
                              Semantics(
                                label: 'Password input field',
                                child: TextFormField(
                                  obscureText: true,
                                  decoration: const InputDecoration(
                                    labelText: 'Password',
                                    labelStyle: TextStyle(
                                      fontSize: 24,
                                      color: Color(0xFFB0A6A6),
                                    ),
                                  ),
                                ),
                              ),
                            ],
                          ),
                        ),
                        const SizedBox(height: 20),
                        Center(
                          child: TextButton(
                            onPressed: () {},
                            child: Text(
                              'Forget Password?',
                              style: GoogleFonts.akatab(
                                fontSize: 20,
                                color: const Color(0xFF1D1E92),
                              ),
                            ),
                          ),
                        ),
                        const SizedBox(height: 34),
                        Center(
                          child: ElevatedButton(
                            onPressed: () {},
                            style: ElevatedButton.styleFrom(
                              backgroundColor: const Color(0xFF74EC34),
                              padding: const EdgeInsets.fromLTRB(44, 16, 44, 28),
                              shape: RoundedRectangleBorder(
                                borderRadius: BorderRadius.circular(20),
                              ),
                            ),
                            child: const Text(
                              'Login',
                              style: TextStyle(
                                fontSize: 40,
                                color: Color(0xFF181313),
                              ),
                            ),
                          ),
                        ),
                      ],
                    ),
                  ),
                ],
              ),
            ),
          ),
        ),
      ),
    );
  }
}


class RegistrationScreen extends StatelessWidget {
  const RegistrationScreen({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      body: Row(
        children: [
          Expanded(
            child: Image.network(
              'https://cdn.builder.io/api/v1/image/assets/TEMP/9b0c7851940eea00f8b7e26a44dc92f3800a2fe4ee3e4f6c4a7b688bdbaead6f?placeholderIfAbsent=true&apiKey=ecbae26a8caa46b68836fb14492d06ac',
              width: 61,
              fit: BoxFit.contain,
            ),
          ),
          Expanded(
            child: Container(
              color: Colors.white,
              padding: const EdgeInsets.symmetric(horizontal: 14, vertical: 24),
              child: const Form(
                child: Column(
                  mainAxisAlignment: MainAxisAlignment.start,
                  crossAxisAlignment: CrossAxisAlignment.center,
                  children: [
                    CustomTextField(
                      label: 'Isi Email Anda',
                      icon: 'https://cdn.builder.io/api/v1/image/assets/TEMP/410055a9146bbf3e36317b93090660fddbb9dd87b5c7c491f01db4af69f9358e?placeholderIfAbsent=true&apiKey=ecbae26a8caa46b68836fb14492d06ac',
                      inputType: TextInputType.emailAddress,
                    ),
                    SizedBox(height: 50),
                    CustomTextField(
                      label: 'Isi Nomor Telepon',
                      icon: 'https://cdn.builder.io/api/v1/image/assets/TEMP/b75eff5953129c4817822ad49a594dfd94576e7d359a1101ecbbbd4c2bf88f56?placeholderIfAbsent=true&apiKey=ecbae26a8caa46b68836fb14492d06ac',
                      inputType: TextInputType.phone,
                    ),
                    SizedBox(height: 50),
                    CustomTextField(
                      label: 'Isi Username',
                      icon: 'https://cdn.builder.io/api/v1/image/assets/TEMP/e5d60d6a759fd68fe7de9580fbdb4a94bb1908e7520a46ed7a7329b5401cb99f?placeholderIfAbsent=true&apiKey=ecbae26a8caa46b68836fb14492d06ac',
                      inputType: TextInputType.text,
                    ),
                    SizedBox(height: 50),
                    CustomTextField(
                      label: 'Isi Password',
                      icon: 'https://cdn.builder.io/api/v1/image/assets/TEMP/fe60eff575433c51060f892366b1ff327f408006efbf329d12796388c13c7a6a?placeholderIfAbsent=true&apiKey=ecbae26a8caa46b68836fb14492d06ac',
                      isPassword: true,
                    ),
                    SizedBox(height: 50),
                    CustomTextField(
                      label: 'Konfirmasi Password',
                      icon: 'https://cdn.builder.io/api/v1/image/assets/TEMP/f9c3729219b10d7bb1c3008b21040cf5b4acc93570bca94821231f373baba1ee?placeholderIfAbsent=true&apiKey=ecbae26a8caa46b68836fb14492d06ac',
                      isPassword: true,
                    ),
                    SizedBox(height: 50),
                    RegisterButton(),
                  ],
                ),
              ),
            ),
          ),
        ],
      ),
    );
  }
}


class CustomTextField extends StatelessWidget {
  final String label;
  final String icon;
  final TextInputType inputType;
  final bool isPassword;

  const CustomTextField({
    super.key,
    required this.label,
    required this.icon,
    this.inputType = TextInputType.text,
    this.isPassword = false,
  });

  @override
  Widget build(BuildContext context) {
    return Column(
      crossAxisAlignment: CrossAxisAlignment.start,
      children: [
        Row(
          children: [
            Image.network(
              icon,
              width: 43,
              fit: BoxFit.contain,
            ),
            const SizedBox(width: 8),
            Text(
              label,
              style: const TextStyle(
                fontSize: 20,
                fontFamily: 'Inter',
              ),
            ),
          ],
        ),
        const SizedBox(height: 16),
        TextFormField(
          keyboardType: inputType,
          obscureText: isPassword,
          decoration: InputDecoration(
            border: OutlineInputBorder(
              borderRadius: BorderRadius.circular(8),
            ),
            labelText: label,
          ),
        ),
      ],
    );
  }
}


class RegisterButton extends StatelessWidget {
  const RegisterButton({super.key});

  @override
  Widget build(BuildContext context) {
    return SizedBox(
      width: 219,
      child: ElevatedButton(
        onPressed: () {},
        style: ElevatedButton.styleFrom(
          backgroundColor: const Color(0xFF74EC34),
          padding: const EdgeInsets.all(22),
          shape: RoundedRectangleBorder(
            borderRadius: BorderRadius.circular(20),
          ),
        ),
        child: const Text(
          'Register',
          style: TextStyle(
            fontSize: 40,
            color: Color(0xFF181313),
          ),
        ),
      ),
    );
  }
}


class ResetPasswordScreen extends StatelessWidget {
  const ResetPasswordScreen({super.key});

  @override
  Widget build(BuildContext context) {
    var GoogleFonts;
    var EmailInputType;
    return Scaffold(
      body: SingleChildScrollView(
        child: Container(
          constraints: const BoxConstraints(maxWidth: 480),
          padding: const EdgeInsets.fromLTRB(14, 24, 44, 198),
          child: Form(
            child: Column(
              crossAxisAlignment: CrossAxisAlignment.start,
              children: [
                Image.asset(
                  'assets/logo.png',
                  width: 61,
                  fit: BoxFit.contain,
                ),
                Padding(
                  padding: const EdgeInsets.only(left: 21, top: 119),
                  child: Text(
                    'Reset Password',
                    style: GoogleFonts.merriweatherSans(
                      fontSize: 36,
                      fontWeight: FontWeight.w800,
                    ),
                  ),
                ),
                Align(
                  alignment: Alignment.centerRight,
                  child: Padding(
                    padding: const EdgeInsets.only(top: 29),
                    child: Text(
                      'Masukkan email anda untuk reset password',
                      style: GoogleFonts.inter(fontSize: 20),
                    ),
                  ),
                ),
                Padding(
                  padding: const EdgeInsets.only(left: 40, top: 37),
                  child: Row(
                    children: [
                      Image.asset(
                        'assets/email_icon.png',
                        width: 43,
                        fit: BoxFit.contain,
                      ),
                      const SizedBox(width: 22),
                      Semantics(
                        label: 'Email input field',
                        child: TextFormField(
                          decoration: InputDecoration(
                            labelText: 'Isi Email Anda',
                            labelStyle: GoogleFonts.inter(fontSize: 20),
                          ),
                          keyboardType: EmailInputType.emailAddress,
                        ),
                      ),
                    ],
                  ),
                ),
                Padding(
                  padding: const EdgeInsets.only(left: 40, top: 30),
                  child: Row(
                    children: [
                      Image.asset(
                        'assets/password_icon.png',
                        width: 43,
                        fit: BoxFit.contain,
                      ),
                      const SizedBox(width: 23),
                      Semantics(
                        label: 'Password input field',
                        child: TextFormField(
                          decoration: InputDecoration(
                            labelText: 'Isi Password Baru',
                            labelStyle: GoogleFonts.inter(fontSize: 20),
                          ),
                          obscureText: true,
                        ),
                      ),
                    ],
                  ),
                ),
                Center(
                  child: Padding(
                    padding: const EdgeInsets.only(top: 57),
                    child: ElevatedButton(
                      onPressed: () {},
                      style: ElevatedButton.styleFrom(
                        backgroundColor: const Color(0xFF74EC34),
                        padding: const EdgeInsets.fromLTRB(59, 19, 59, 34),
                        shape: RoundedRectangleBorder(
                          borderRadius: BorderRadius.circular(20),
                        ),
                        minimumSize: const Size(219, 0),
                      ),
                      child: Text(
                        'Reset',
                        style: GoogleFonts.inter(
                          fontSize: 40,
                          color: const Color(0xFF181313),
                        ),
                      ),
                    ),
                  ),
                ),
              ],
            ),
          ),
        ),
      ),
    );
  }
}


final ThemeData resetPasswordTheme = ThemeData(
  primaryColor: const Color(0xFF74EC34),
  scaffoldBackgroundColor: Colors.white,
  textTheme: const TextTheme(
    bodyLarge: TextStyle(
      color: Colors.black,
      fontSize: 20,
    ),
  ),
  inputDecorationTheme: InputDecorationTheme(
    border: OutlineInputBorder(
      borderRadius: BorderRadius.circular(8),
    ),
    focusedBorder: OutlineInputBorder(
      borderRadius: BorderRadius.circular(8),
      borderSide: const BorderSide(color: Color(0xFF74EC34)),
    ),
  ),
);



class HomeScreen extends StatelessWidget {
  const HomeScreen({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      body: SingleChildScrollView(
        child: Container(
          padding: const EdgeInsets.fromLTRB(10, 15, 0, 0),
          color: Colors.white,
          child: const Column(
            crossAxisAlignment: CrossAxisAlignment.start,
            children: [
              LocationBar(),
              SearchBarWidget(),
              SizedBox(height: 26),
              Text(
                'Kategori Barang',
                style: TextStyle(
                  fontSize: 20,
                  fontWeight: FontWeight.w800,
                  fontFamily: 'Merriweather Sans',
                ),
              ),
              CategoryGrid(),
              SizedBox(height: 79),
              Text(
                'Barang Diskon',
                style: TextStyle(
                  fontSize: 20,
                  fontWeight: FontWeight.w800,
                  fontFamily: 'Merriweather Sans',
                ),
              ),
              DiscountProducts(),
            ],
          ),
        ),
      ),
    );
  }
}



class LocationBar extends StatelessWidget {
  const LocationBar({super.key});

  @override
  Widget build(BuildContext context) {
    return Row(
      children: [
        Container(
          padding: const EdgeInsets.symmetric(horizontal: 11, vertical: 10),
          decoration: BoxDecoration(
            color: Colors.black,
            borderRadius: BorderRadius.circular(30),
          ),
          child: Row(
            children: [
              Image.asset(
                'assets/images/location_icon.png',
                width: 20,
                height: 17,
              ),
              const SizedBox(width: 9),
              const Text(
                'Jl. Lematang VI No. 305',
                style: TextStyle(
                  color: Colors.white,
                  fontSize: 16,
                  fontFamily: 'Inter',
                ),
              ),
            ],
          ),
        ),
        const SizedBox(width: 15),
        Image.asset(
          'assets/images/notification.png',
          width: 43,
          height: 39,
        ),
        const SizedBox(width: 7),
        Image.asset(
          'assets/images/profile.png',
          width: 64,
          height: 62,
        ),
      ],
    );
  }
}


class SearchBarWidget extends StatelessWidget {
  const SearchBarWidget({super.key});

  @override
  Widget build(BuildContext context) {
    return Container(
      margin: const EdgeInsets.only(top: 10),
      padding: const EdgeInsets.symmetric(horizontal: 19, vertical: 11),
      decoration: BoxDecoration(
        color: const Color(0xFFD9D9D9),
        borderRadius: BorderRadius.circular(30),
      ),
      child: Row(
        children: [
          Image.asset(
            'assets/images/search_icon.png',
            width: 24,
            height: 24,
          ),
          const SizedBox(width: 16),
          const Expanded(
            child: TextField(
              decoration: InputDecoration(
                hintText: 'Cari barang mu disini...',
                border: InputBorder.none,
                hintStyle: TextStyle(
                  fontSize: 16,
                  fontFamily: 'Inter',
                ),
              ),
            ),
          ),
        ],
      ),
    );
  }
}



class CategoryGrid extends StatelessWidget {
  const CategoryGrid({super.key});

  @override
  Widget build(BuildContext context) {
    return Container(
      margin: const EdgeInsets.only(top: 43),
      child: Row(
        crossAxisAlignment: CrossAxisAlignment.start,
        children: [
          Expanded(
            child: Column(
              children: [
                _buildCategoryRow([
                  const CategoryItem('Bahan Pokok', 'assets/images/category1.png'),
                  const CategoryItem('Minuman', 'assets/images/category2.png'),
                ]),
                const SizedBox(height: 50),
                _buildCategoryRow([
                  const CategoryItem('Buah & Sayuran', 'assets/images/category3.png'),
                  const CategoryItem('Roti', 'assets/images/category4.png'),
                ]),
                const SizedBox(height: 17),
                _buildCategoryRow([
                  const CategoryItem('Obat & Vitamin', 'assets/images/category5.png'),
                  const CategoryItem('Makanan Hewan', 'assets/images/category6.png'),
                ]),
              ],
            ),
          ),
          const SizedBox(
            width: 100,
            child: Column(
              children: [
                CategoryItem('Makanan Instan', 'assets/images/category7.png'),
                SizedBox(height: 34),
                CategoryItem('Daging & Hasil Laut', 'assets/images/category8.png'),
                SizedBox(height: 32),
                CategoryItem('Kategori Lainnya', 'assets/images/category9.png'),
              ],
            ),
          ),
        ],
      ),
    );
  }

  Widget _buildCategoryRow(List<Widget> items) {
    return Row(
      mainAxisAlignment: MainAxisAlignment.spaceAround,
      children: items,
    );
  }
}

class CategoryItem extends StatelessWidget {
  final String title;
  final String imagePath;

  const CategoryItem(this.title, this.imagePath, {super.key});

  @override
  Widget build(BuildContext context) {
    return Column(
      children: [
        Image.asset(
          imagePath,
          width: 100,
          height: 100,
        ),
        const SizedBox(height: 9),
        Text(
          title,
          style: const TextStyle(
            fontSize: 15,
            fontFamily: 'Merriweather Sans',
          ),
          textAlign: TextAlign.center,
        ),
      ],
    );
  }
}



class DiscountProducts extends StatelessWidget {
  const DiscountProducts({super.key});

  @override
  Widget build(BuildContext context) {
    return Container(
      height: 280,
      margin: const EdgeInsets.only(top: 30),
      child: ListView(
        scrollDirection: Axis.horizontal,
        children: const [
          ProductCard(
            image: 'assets/images/product1.png',
            name: 'Greenfield 1000ml',
            originalPrice: '24.000',
            discountPrice: '19.200',
          ),
          ProductCard(
            image: 'assets/images/product2.png',
            name: 'Roma Biskuit Kelapa',
            originalPrice: '11.000',
            discountPrice: '10.200',
          ),
          ProductCard(
            image: 'assets/images/product3.png',
            name: 'Redbull 250ml',
            originalPrice: '23.000',
            discountPrice: '19.900',
          ),
          ProductCard(
            image: 'assets/images/product4.png',
            name: 'Dancow Full Cream 800g',
            originalPrice: '113.400',
            discountPrice: '100.000',
          ),
          ProductCard(
            image: 'assets/images/product5.png',
            name: 'Segitiga Biru Tepung Terigu',
            originalPrice: '15.200',
            discountPrice: '12.300',
          ),
          ProductCard(
            image: 'assets/images/product6.png',
            name: 'Minuman Soda',
            originalPrice: '12.000',
            discountPrice: '9.600',
          ),
        ],
      ),
    );
  }
}

class ProductCard extends StatelessWidget {
  final String image;
  final String name;
  final String originalPrice;
  final String discountPrice;

  const ProductCard({super.key,
    required this.image,
    required this.name,
    required this.originalPrice,
    required this.discountPrice,
  });

  @override
  Widget build(BuildContext context) {
    return Container(
      width: 137,
      margin: const EdgeInsets.only(right: 78),
      child: Column(
        crossAxisAlignment: CrossAxisAlignment.start,
        children: [
          Image.asset(
            image,
            width: 123,
            height: 123,
            fit: BoxFit.contain,
          ),
          Text(
            name,
            style: const TextStyle(
              fontSize: 24,
              fontFamily: 'Merriweather Sans',
            ),
          ),
          Text(
            'Rp $originalPrice',
            style: const TextStyle(
              fontSize: 16,
              fontFamily: 'Merriweather Sans',
              decoration: TextDecoration.lineThrough,
            ),
          ),
          Text(
            'Rp $discountPrice',
            style: const TextStyle(
              fontSize: 20,
              fontFamily: 'Merriweather Sans',
            ),
          ),
          Row(
            mainAxisAlignment: MainAxisAlignment.spaceBetween,
            children: [
              Container(
                width: 16,
                height: 3,
                color: Colors.black,
              ),
              Container(
                width: 14,
                height: 14,
                color: Colors.black,
              ),
            ],
          ),
        ],
      ),
    );
  }
}



class ConfirmationScreen extends StatelessWidget {
  const ConfirmationScreen({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      body: SingleChildScrollView(
        child: Container(
          constraints: const BoxConstraints(maxWidth: 480),
          padding: const EdgeInsets.symmetric(horizontal: 9, vertical: 23),
          color: Colors.white,
          child: const Column(
            crossAxisAlignment: CrossAxisAlignment.start,
            children: [
              HeaderSection(),
              AddressSection(),
              ItemsSection(),
              PaymentDetails(),
              PaymentButton(),
              PromoCard(),
              DiscountedItems(),
            ],
          ),
        ),
      ),
    );
  }
}



class HeaderSection extends StatelessWidget {
  const HeaderSection({super.key});

  @override
  Widget build(BuildContext context) {
    return Row(
      children: [
        Image.network(
          'https://cdn.builder.io/api/v1/image/assets/TEMP/94fc0ccc575ee31d913c782f0300b62c7a81112310d40782c08944f191dbe542?placeholderIfAbsent=true&apiKey=ecbae26a8caa46b68836fb14492d06ac',
          width: 61,
          fit: BoxFit.contain,
        ),
        const Text(
          'Konfirmasi belanjaan',
          style: TextStyle(
            fontSize: 20,
            fontWeight: FontWeight.w800,
            fontFamily: 'Merriweather Sans',
          ),
        ),
      ],
    );
  }
}



class AddressSection extends StatelessWidget {
  const AddressSection({super.key});

  @override
  Widget build(BuildContext context) {
    return Padding(
      padding: const EdgeInsets.only(left: 12, top: 33),
      child: Row(
        children: [
          Column(
            crossAxisAlignment: CrossAxisAlignment.start,
            children: [
              const Text(
                'Alamat pengiriman',
                style: TextStyle(
                  fontFamily: 'Inter',
                  fontSize: 15,
                ),
              ),
              const SizedBox(height: 7),
              const Text(
                'Jl. Lematang VI No. 305',
                style: TextStyle(
                  fontFamily: 'Inter',
                  fontSize: 24,
                  fontWeight: FontWeight.w700,
                ),
              ),
              const SizedBox(height: 7),
              Container(
                padding: const EdgeInsets.symmetric(horizontal: 8, vertical: 6),
                decoration: BoxDecoration(
                  borderRadius: BorderRadius.circular(30),
                  color: const Color(0xFFD9D9D9),
                ),
                child: Row(
                  children: [
                    Image.network(
                      'https://cdn.builder.io/api/v1/image/assets/TEMP/7fde9a8dfac91b3b1361173617cc398a722e4a2d653b35c16b444b707fa3af79?placeholderIfAbsent=true&apiKey=ecbae26a8caa46b68836fb14492d06ac',
                      width: 24,
                      height: 24,
                    ),
                    const SizedBox(width: 6),
                    const Text(
                      'Catatan',
                      style: TextStyle(
                        fontSize: 20,
                        fontFamily: 'Inter',
                      ),
                    ),
                  ],
                ),
              ),
            ],
          ),
          const Spacer(),
          Container(
            padding: const EdgeInsets.fromLTRB(5, 10, 5, 22),
            decoration: BoxDecoration(
              borderRadius: BorderRadius.circular(30),
              color: const Color(0xFF50E500),
            ),
            child: const Text(
              'Ubah alamat',
              style: TextStyle(
                fontSize: 20,
                fontFamily: 'Inter',
              ),
            ),
          ),
        ],
      ),
    );
  }
}



class ItemsSection extends StatelessWidget {
  const ItemsSection({super.key});

  @override
  Widget build(BuildContext context) {
    return Padding(
      padding: const EdgeInsets.only(left: 16, top: 67),
      child: Column(
        children: [
          _buildItemCard(
            image: 'https://cdn.builder.io/api/v1/image/assets/TEMP/361a9973da17612905020681bb9f154daef16cd1bd52b67c2cb0a57a934721bb?placeholderIfAbsent=true&apiKey=ecbae26a8caa46b68836fb14492d06ac',
            title: 'Kraft Keju High Calcium Singles 5 Slice',
            price: 'Rp. 14.000',
          ),
          const SizedBox(height: 34),
          _buildItemCard(
            image: 'https://cdn.builder.io/api/v1/image/assets/TEMP/2d881ea65d9dc19d7dd97b517c54628d0ebd5aed03d80e41102ac817fa057074?placeholderIfAbsent=true&apiKey=ecbae26a8caa46b68836fb14492d06ac',
            title: 'Mama Lemon Jeruk Nipis 680 ml',
            price: 'Rp. 10.000',
          ),
        ],
      ),
    );
  }

  Widget _buildItemCard({
    required String image,
    required String title,
    required String price,
  }) {
    return Row(
      children: [
        Image.network(
          image,
          width: 97,
          fit: BoxFit.contain,
        ),
        const SizedBox(width: 13),
        Expanded(
          child: Column(
            crossAxisAlignment: CrossAxisAlignment.start,
            children: [
              Text(
                title,
                style: const TextStyle(
                  fontFamily: 'Inter',
                  fontWeight: FontWeight.w700,
                  fontSize: 16,
                ),
              ),
              const SizedBox(height: 8),
              Row(
                mainAxisAlignment: MainAxisAlignment.spaceBetween,
                children: [
                  Text(
                    price,
                    style: const TextStyle(
                      fontFamily: 'Inter',
                      fontSize: 16,
                    ),
                  ),
                  Row(
                    children: [
                      Image.network(
                        'https://cdn.builder.io/api/v1/image/assets/TEMP/eddee182f8f34dff5d1fef442298b8e2b2dd2c11883f804c932af2fe99f7af83?placeholderIfAbsent=true&apiKey=ecbae26a8caa46b68836fb14492d06ac',
                        width: 20,
                        height: 20,
                      ),
                      const SizedBox(width: 20),
                      const Text(
                        '1',
                        style: TextStyle(
                          fontWeight: FontWeight.w700,
                        ),
                      ),
                      const SizedBox(width: 20),
                      Image.network(
                        'https://cdn.builder.io/api/v1/image/assets/TEMP/6fef70614e330c3e433598b8596729273697d901bbe8c957c06daaada514dc3d?placeholderIfAbsent=true&apiKey=ecbae26a8caa46b68836fb14492d06ac',
                        width: 30,
                        height: 30,
                      ),
                    ],
                  ),
                ],
              ),
            ],
          ),
        ),
      ],
    );
  }
}



class PaymentDetails extends StatelessWidget {
  const PaymentDetails({super.key});

  @override
  Widget build(BuildContext context) {
    return const Padding(
      padding: EdgeInsets.only(left: 22, top: 67),
      child: Column(
        crossAxisAlignment: CrossAxisAlignment.start,
        children: [
          Text(
            'Detail Pembayaran',
            style: TextStyle(
              fontSize: 20,
              fontWeight: FontWeight.w800,
            ),
          ),
          SizedBox(height: 31),
          Padding(
            padding: EdgeInsets.only(right: 20),
            child: Row(
              mainAxisAlignment: MainAxisAlignment.spaceBetween,
              children: [
                Column(
                  crossAxisAlignment: CrossAxisAlignment.start,
                  children: [
                    Text(
                      'Harga',
                      style: TextStyle(
                        fontFamily: 'Inter',
                        fontSize: 16,
                        fontWeight: FontWeight.w600,
                      ),
                    ),
                    SizedBox(height: 19),
                    Text(
                      'Biaya Ongkir',
                      style: TextStyle(
                        fontFamily: 'Inter',
                        fontSize: 16,
                        fontWeight: FontWeight.w600,
                      ),
                    ),
                    SizedBox(height: 18),
                    Text(
                      'Total Harga',
                      style: TextStyle(
                        fontFamily: 'Inter',
                        fontSize: 16,
                        fontWeight: FontWeight.w600,
                      ),
                    ),
                  ],
                ),
                Column(
                  crossAxisAlignment: CrossAxisAlignment.end,
                  children: [
                    Text(
                      'Rp. 24.000',
                      style: TextStyle(
                        fontFamily: 'Inter',
                        fontSize: 16,
                        fontWeight: FontWeight.w600,
                      ),
                    ),
                    SizedBox(height: 18),
                    Row(
                      children: [
                        Text(
                          '̶R̶p̶.̶ ̶1̶0̶.̶0̶0̶0̶',
                          style: TextStyle(
                            fontFamily: 'Inter',
                            fontSize: 16,
                            fontWeight: FontWeight.w400,
                          ),
                        ),
                        SizedBox(width: 6),
                        Text(
                          'Rp. 2.000',
                          style: TextStyle(
                            fontFamily: 'Inter',
                            fontSize: 16,
                            fontWeight: FontWeight.w600,
                          ),
                        ),
                      ],
                    ),
                    SizedBox(height: 13),
                    Text(
                      'Rp. 26.000',
                      style: TextStyle(
                        fontFamily: 'Inter',
                        fontSize: 16,
                        fontWeight: FontWeight.w600,
                      ),
                    ),
                  ],
                ),
              ],
            ),
          ),
        ],
      ),
    );
  }
}



class PaymentButton extends StatelessWidget {
  const PaymentButton({super.key});

  @override
  Widget build(BuildContext context) {
    return Container(
      margin: const EdgeInsets.only(top: 18),
      padding: const EdgeInsets.fromLTRB(24, 13, 24, 22),
      decoration: BoxDecoration(
        borderRadius: BorderRadius.circular(30),
        color: const Color(0xFF74EC34),
      ),
      child: Row(
        children: [
          const Expanded(
            child: Text(
              'Pilih Pembayaran',
              style: TextStyle(
                fontSize: 20,
                fontFamily: 'Inter',
              ),
            ),
          ),
          Image.network(
            'https://cdn.builder.io/api/v1/image/assets/TEMP/788694c57706790a86a47af6a59e34aa2c484e0be15262ba87e11440d086e672?placeholderIfAbsent=true&apiKey=ecbae26a8caa46b68836fb14492d06ac',
            width: 30,
          ),
          const Text(
            'Rp. 26.000',
            style: TextStyle(
              fontSize: 16,
              fontFamily: 'Inter',
            ),
          ),
        ],
      ),
    );
  }
}


class PromoCard extends StatelessWidget {
  const PromoCard({super.key});

  @override
  Widget build(BuildContext context) {
    return Container(
      margin: const EdgeInsets.only(top: 18),
      padding: const EdgeInsets.symmetric(horizontal: 23, vertical: 29),
      decoration: BoxDecoration(
        borderRadius: BorderRadius.circular(40),
        color: const Color(0xFFE0E5DD),
        boxShadow: [
          BoxShadow(
            color: Colors.black.withOpacity(0.25),
            blurRadius: 4,
            offset: const Offset(0, 4),
          ),
        ],
      ),
      child: Row(
        children: [
          Image.network(
            'https://cdn.builder.io/api/v1/image/assets/TEMP/94193aefe8fa9f6e7a4c4de4d36d5684b9cb29fbca0bd2321f7298734f874821?placeholderIfAbsent=true&apiKey=ecbae26a8caa46b68836fb14492d06ac',
            width: 47,
          ),
          const Expanded(
            child: Text(
              'Promo mu sudah terpakai!',
              style: TextStyle(
                fontSize: 24,
                fontWeight: FontWeight.w800,
                fontFamily: 'Inter',
              ),
            ),
          ),
          Image.network(
            'https://cdn.builder.io/api/v1/image/assets/TEMP/dd3fdd28494b60dafbc16c07358bdf643a2585360d481ae83af9ba234dcf0298?placeholderIfAbsent=true&apiKey=ecbae26a8caa46b68836fb14492d06ac',
            width: 43,
          ),
        ],
      ),
    );
  }
}


class DiscountedItems extends StatelessWidget {
  const DiscountedItems({super.key});

  @override
  Widget build(BuildContext context) {
    return Padding(
      padding: const EdgeInsets.only(top: 38),
      child: Row(
        mainAxisAlignment: MainAxisAlignment.spaceBetween,
        children: [
          _buildDiscountedItem(
            image: 'https://cdn.builder.io/api/v1/image/assets/TEMP/dbb991388448e4a2504168824633fe316c4e86eaf3a240782d9fa9f4370937cd?placeholderIfAbsent=true&apiKey=ecbae26a8caa46b68836fb14492d06ac',
            title: 'Segitiga Biru Tepung Terigu',
            originalPrice: 'Rp 15.200',
            discountedPrice: 'Rp 12.300',
          ),
          _buildDiscountedItem(
            image: 'https://cdn.builder.io/api/v1/image/assets/TEMP/1ec530b1798777e91760e6cf759975bbb18ea4249ec924ec6e7e6c7ea952b05d?placeholderIfAbsent=true&apiKey=ecbae26a8caa46b68836fb14492d06ac',
            title: 'Greenfield 1000ml',
            originalPrice: 'Rp 24.000',
            discountedPrice: 'Rp 19.200',
          ),
        ],
      ),
    );
  }

  Widget _buildDiscountedItem({
    required String image,
    required String title,
    required String originalPrice,
    required String discountedPrice,
  }) {
    return Column(
      crossAxisAlignment: CrossAxisAlignment.start,
      children: [
        const Text(
          'Barang Diskon',
          style: TextStyle(
            fontSize: 24,
            fontWeight: FontWeight.w800,
            fontFamily: 'Inter',
          ),
        ),
        Image.network(
          image,
          width: 123,
        ),
        Text(
          title,
          style: const TextStyle(
            fontSize: 24,
            fontFamily: 'Inter',
          ),
        ),
        Text(
          originalPrice,
          style: const TextStyle(
            fontSize: 16,
            decoration: TextDecoration.lineThrough,
            fontFamily: 'Inter',
          ),
        ),
        Text(
          discountedPrice,
          style: const TextStyle(
            fontSize: 20,
            fontFamily: 'Inter',
          ),
        ),
        Row(
          children: [
            Container(
              width: 16,
              height: 2,
              color: Colors.black,
            ),
            const SizedBox(width: 23),
            const Text(
              '0',
              style: TextStyle(
                fontSize: 20,
                fontFamily: 'Inter',
              ),
            ),
            const SizedBox(width: 23),
            Image.network(
              'https://cdn.builder.io/api/v1/image/assets/TEMP/dee0c722fabefd79f142a8f04654d86c5f32b82900fca96a3d18cf03b9e94577?placeholderIfAbsent=true&apiKey=ecbae26a8caa46b68836fb14492d06ac',
              width: 14,
            ),
          ],
        ),
      ],
    );
  }
}


class PaymentMethodsScreen extends StatelessWidget {
  const PaymentMethodsScreen({super.key});

  @override
  Widget build(BuildContext context) {
    var GoogleFonts;
    return Scaffold(
      body: Container(
        color: Colors.white,
        child: SafeArea(
          child: Padding(
            padding: const EdgeInsets.fromLTRB(8, 20, 25, 73),
            child: Column(
              crossAxisAlignment: CrossAxisAlignment.start,
              children: [
                Row(
                  children: [
                    Image.network(
                      'https://cdn.builder.io/api/v1/image/assets/TEMP/94fc0ccc575ee31d913c782f0300b62c7a81112310d40782c08944f191dbe542?placeholderIfAbsent=true&apiKey=ecbae26a8caa46b68836fb14492d06ac',
                      width: 61,
                      fit: BoxFit.contain,
                    ),
                    Text(
                      'Metode Pembayaran',
                      style: GoogleFonts.merriweatherSans(
                        fontSize: 20,
                        fontWeight: FontWeight.w800,
                      ),
                    ),
                  ],
                ),
                const SizedBox(height: 94),
                const PaymentMethodItem(
                  imagePath: 'https://cdn.builder.io/api/v1/image/assets/TEMP/cf0b2fa7023d9bebc029e239223bb2f9f877fc7a168f5d3fe0eea292e515ef0b?placeholderIfAbsent=true&apiKey=ecbae26a8caa46b68836fb14492d06ac',
                  title: 'E-Wallet',
                  imageWidth: 80,
                ),
                const SizedBox(height: 50),
                const PaymentMethodItem(
                  imagePath: 'https://cdn.builder.io/api/v1/image/assets/TEMP/7027d51ffb11d3aa49f1e79042d65afcd1d2980716c5115bf6cc72f673fb8a06?placeholderIfAbsent=true&apiKey=ecbae26a8caa46b68836fb14492d06ac',
                  title: 'Bank',
                  imageWidth: 79,
                ),
                const SizedBox(height: 50),
                const PaymentMethodItem(
                  imagePath: 'https://cdn.builder.io/api/v1/image/assets/TEMP/22e5cb19edb4b976cf290e8fd1298fd038e89378baf68b247e6ccbc16a3d0a99?placeholderIfAbsent=true&apiKey=ecbae26a8caa46b68836fb14492d06ac',
                  title: 'E-Wallet',
                  imageWidth: 72,
                ),
                const SizedBox(height: 59),
                const PaymentMethodItem(
                  imagePath: 'https://cdn.builder.io/api/v1/image/assets/TEMP/86e8ffd1cfdba66aa7d8498d638d4249d93fdb864ffd0c66ae1ecbcc52c8c50f?placeholderIfAbsent=true&apiKey=ecbae26a8caa46b68836fb14492d06ac',
                  title: 'Cash',
                  imageWidth: 107,
                ),
                const SizedBox(height: 86),
                Container(
                  width: double.infinity,
                  padding: const EdgeInsets.symmetric(vertical: 14),
                  decoration: BoxDecoration(
                    color: const Color(0xFF74EC34),
                    borderRadius: BorderRadius.circular(30),
                  ),
                  child: Center(
                    child: Text(
                      'Sudah Bayar',
                      style: GoogleFonts.merriweatherSans(
                        fontSize: 36,
                        fontWeight: FontWeight.w400,
                      ),
                    ),
                  ),
                ),
              ],
            ),
          ),
        ),
      ),
    );
  }
}



class PaymentMethodItem extends StatelessWidget {
  final String imagePath;
  final String title;
  final double imageWidth;

  const PaymentMethodItem({
    super.key,
    required this.imagePath,
    required this.title,
    required this.imageWidth,
  });

  @override
  Widget build(BuildContext context) {
    var GoogleFonts;
    return Container(
      padding: const EdgeInsets.symmetric(horizontal: 28, vertical: 5),
      decoration: BoxDecoration(
        color: const Color(0xFFD9D9D9),
        borderRadius: BorderRadius.circular(40),
      ),
      child: Row(
        children: [
          Image.network(
            imagePath,
            width: imageWidth,
            fit: BoxFit.contain,
          ),
          const SizedBox(width: 20),
          Expanded(
            child: Text(
              title,
              style: GoogleFonts.merriweatherSans(
                fontSize: 24,
                fontWeight: FontWeight.w700,
              ),
            ),
          ),
        ],
      ),
    );
  }
}



class OrderStatusScreen extends StatelessWidget {
  const OrderStatusScreen({super.key});

  @override
  Widget build(BuildContext context) {
    var GoogleFonts;
    return Scaffold(
      body: Container(
        color: Colors.white,
        child: SingleChildScrollView(
          child: Container(
            constraints: const BoxConstraints(maxWidth: 480),
            width: double.infinity,
            padding: const EdgeInsets.fromLTRB(33, 44, 33, 96),
            child: Column(
              crossAxisAlignment: CrossAxisAlignment.start,
              children: [
                Text(
                  'Status Order',
                  style: GoogleFonts.merriweatherSans(
                    fontSize: 24,
                    fontWeight: FontWeight.w800,
                    color: Colors.black,
                  ),
                ),
                const SizedBox(height: 34),
                Text(
                  'Pesanan mu sudah mau sampai!',
                  style: GoogleFonts.merriweatherSans(
                    fontSize: 36,
                    fontWeight: FontWeight.w700,
                    color: Colors.black,
                  ),
                ),
                const SizedBox(height: 15),
                Text(
                  'Terima kasih sudah memesan di aplikasi kami ya!',
                  style: GoogleFonts.merriweatherSans(
                    fontSize: 15,
                    fontWeight: FontWeight.w700,
                    color: Colors.black,
                  ),
                ),
                const SizedBox(height: 76),
                const StatusItem(
                  imagePath: 'assets/courier_arrived.png',
                  text: 'Kurir sudah sampai di toko',
                  imageWidth: 49,
                  imageAspectRatio: 0.94,
                ),
                const SizedBox(height: 54),
                const StatusItem(
                  imagePath: 'assets/order_prepared.png',
                  text: 'Pesanan sudah disiapkan',
                  imageWidth: 43,
                  imageAspectRatio: 0.83,
                ),
                const SizedBox(height: 50),
                const StatusItem(
                  imagePath: 'assets/driver_otw.png',
                  text: 'Driver sedang menuju lokasi tujuan',
                  imageWidth: 49,
                  imageAspectRatio: 0.8,
                ),
                const SizedBox(height: 110),
                Center(
                  child: ElevatedButton(
                    onPressed: () {
                      Navigator.pop(context);
                    },
                    style: ElevatedButton.styleFrom(
                      backgroundColor: const Color(0xFF74EC34),
                      padding: const EdgeInsets.symmetric(horizontal: 70, vertical: 27),
                      shape: RoundedRectangleBorder(
                        borderRadius: BorderRadius.circular(30),
                      ),
                      minimumSize: const Size(374, 0),
                    ),
                    child: Text(
                      'Kembali ke Halaman',
                      style: GoogleFonts.merriweatherSans(
                        fontSize: 20,
                        color: Colors.black,
                      ),
                    ),
                  ),
                ),
              ],
            ),
          ),
        ),
      ),
    );
  }
}



class StatusItem extends StatelessWidget {
  final String imagePath;
  final String text;
  final double imageWidth;
  final double imageAspectRatio;

  const StatusItem({
    super.key,
    required this.imagePath,
    required this.text,
    required this.imageWidth,
    required this.imageAspectRatio,
  });

  @override
  Widget build(BuildContext context) {
    var GoogleFonts;
    return Padding(
      padding: const EdgeInsets.only(left: 28),
      child: Row(
        children: [
          Image.asset(
            imagePath,
            width: imageWidth,
            height: imageWidth / imageAspectRatio,
            fit: BoxFit.contain,
          ),
          const SizedBox(width: 14),
          Expanded(
            child: Text(
              text,
              style: GoogleFonts.merriweatherSans(
                fontSize: 16,
                color: Colors.black,
                fontWeight: FontWeight.w400,
              ),
            ),
          ),
        ],
      ),
    );
  }
}
