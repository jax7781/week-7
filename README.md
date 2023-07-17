# week-7
Scripts for Week 7
def median(numbers):
    if len(numbers) == 0:
        return 0

    sorted_numbers = sorted(numbers)
    mid_index = len(sorted_numbers) // 2

    if len(sorted_numbers) % 2 == 0:
        return (sorted_numbers[mid_index - 1] + sorted_numbers[mid_index]) / 2
    else:
        return sorted_numbers[mid_index]


def mode(numbers):
    if len(numbers) == 0:
        return 0

    counts = {}
    for num in numbers:
        counts[num] = counts.get(num, 0) + 1

    max_count = max(counts.values())
    modes = [num for num, count in counts.items() if count == max_count]

    if len(modes) == len(numbers):
        return 0
    else:
        return modes


def mean(numbers):
    if len(numbers) == 0:
        return 0

    return sum(numbers) / len(numbers)


def main():
    test_numbers = [4, 2, 9, 6, 2, 5, 3, 9, 1, 5]  # Example list of numbers for testing

    print("Numbers:", test_numbers)
    print("Median:", median(test_numbers))
    print("Mode:", mode(test_numbers))
    print("Mean:", mean(test_numbers))


if __name__ == '__main__':
    main()

def read_file(filename):
    try:
        with open(filename, 'r') as file:
            lines = file.readlines()
        return lines
    except FileNotFoundError:
        print("File not found.")
        return []


def main():
    filename = input("Enter the filename: ")
    lines = read_file(filename)

    num_lines = len(lines)

    while True:
        print(f"\nNumber of lines in the file: {num_lines}")
        line_number = int(input("Enter a line number (0 to quit): "))

        if line_number == 0:
            print("Exiting the program.")
            break

        if 1 <= line_number <= num_lines:
            print(f"Line {line_number}: {lines[line_number - 1]}")
        else:
            print("Invalid line number. Please try again.")


if __name__ == '__main__':
    main()

