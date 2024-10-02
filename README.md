program diferencia_datos
    implicit none
    integer :: i, n
    real, allocatable :: col11(:), col22(:)
    real allocatable :: col1(:), col2(:), dif(:)
n = 100000
    allocate(col11(n), col22(n))
    allocate(col1(n), col2(n), dif(n))
    open(100, file = 'position.dat')
    open(200, file = 'position0.dat')
    open(300, file = 'diferencias.dat')
    do i = 1, n
        read(100,*) col11(i), col22(i)
        read(200,*) col1(i), col2(i)
        dif(i) = abs(col22(i) - col2(i))
    end do

   do i = 1, n
        write(300,*) col1(i), dif(i)
    end do
    close(100)
    close(200)
    close(300)

end program diferencia_datos
