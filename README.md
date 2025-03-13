# project
hw1_binary_hex_converter

def decimal_to_binary(n):
    binary = ""
    for i in range(7, -1, -1):  # 2^7 to 2^0
        bit = (n >> i) & 1  # 取得當前位元值
        binary += str(bit)
    return binary


def binary_to_hex(binary):
    hex_map = {
        "0000": "0", "0001": "1", "0010": "2", "0011": "3",
        "0100": "4", "0101": "5", "0110": "6", "0111": "7",
        "1000": "8", "1001": "9", "1010": "A", "1011": "B",
        "1100": "C", "1101": "D", "1110": "E", "1111": "F"
    }
    return hex_map[binary[:4]] + hex_map[binary[4:]]


def main():
    while True:
        try:
            decimal = int(input("Enter a decimal number (0-255): "))
            if 0 <= decimal <= 255:
                binary = decimal_to_binary(decimal)
                hexadecimal = binary_to_hex(binary)
                print(f"Binary: {binary}")
                print(f"Hexadecimal: {hexadecimal}")
            else:
                print("Please enter a number between 0 and 255.")
        except ValueError:
            print("Invalid input. Please enter an integer.")


if __name__ == "__main__":
    main()
