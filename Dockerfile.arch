FROM archlinux/base

# Per https://github.com/diggit/docker_arch_arm-none-eabi-gcc/blob/master/Dockerfile
RUN pacman -Sy --noconfirm && \
    pacman -S git arm-none-eabi-gcc arm-none-eabi-newlib cmake make --noconfirm

