CXX = i686-elf-c++
CXXFLAGS = 
test-07-throw-clean-up-rethrow.elf: test-07-throw-clean-up-rethrow.o
	$(CXX) -ffreestanding -std=c++14 -mno-red-zone  -ffreestanding -nostdlib -Wl,-T,/opt/libsupcxx/boot/i686/kernel.ld -z max-page-size=0x1000 $<  -o $@ -Wl,--whole-archive ../i686-build/boot/i686/libboot_first.a -Wl,--no-whole-archive ../i686-build/io/libio.a ../i686-build/libsupcxx/src/libsupcxx.a -lgcc ../i686-build/libruncxx/libruncxx.a -Wl,--whole-archive ../i686-build/boot/i686/libboot_last.a -Wl,--no-whole-archive

test-07-throw-clean-up-rethrow.o: test-07-throw-clean-up-rethrow.cc
	$(CXX) -I/opt/libsupcxx/ -I/opt/libsupcxx/libsupcxx/include  -ffreestanding -std=c++14 -mno-red-zone -c $<

clean:
	rm -rf *.o *.elf

qemu:
	qemu-system-i386 -kernel test-07-throw-clean-up-rethrow.elf

