# ex03a-JPHorist
-- phpMyAdmin SQL Dump
-- version 4.9.0.1
-- https://www.phpmyadmin.net/
--
-- Host: localhost
-- Generation Time: Oct 01, 2019 at 01:30 AM
-- Server version: 10.4.6-MariaDB
-- PHP Version: 7.3.9

SET SQL_MODE = "NO_AUTO_VALUE_ON_ZERO";
SET AUTOCOMMIT = 0;
START TRANSACTION;
SET time_zone = "+00:00";


/*!40101 SET @OLD_CHARACTER_SET_CLIENT=@@CHARACTER_SET_CLIENT */;
/*!40101 SET @OLD_CHARACTER_SET_RESULTS=@@CHARACTER_SET_RESULTS */;
/*!40101 SET @OLD_COLLATION_CONNECTION=@@COLLATION_CONNECTION */;
/*!40101 SET NAMES utf8mb4 */;

--
-- Database: `WPEX03`
--

-- --------------------------------------------------------

--
-- Table structure for table `ASSIGNMENT`
--

CREATE TABLE `ASSIGNMENT` (
  `ProjectID` int(11) NOT NULL,
  `EmployeeNumber` int(11) NOT NULL,
  `HoursWorked` decimal(6,2) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

--
-- Dumping data for table `ASSIGNMENT`
--

INSERT INTO `ASSIGNMENT` (`ProjectID`, `EmployeeNumber`, `HoursWorked`) VALUES
(1000, 1, '30.00'),
(1000, 6, '50.00'),
(1000, 10, '50.00'),
(1000, 16, '75.00'),
(1000, 17, '75.00'),
(1100, 1, '30.00'),
(1100, 6, '75.00'),
(1100, 10, '55.00'),
(1100, 11, '55.00'),
(1200, 3, '20.00'),
(1200, 6, '40.00'),
(1200, 7, '45.00'),
(1200, 8, '45.00'),
(1300, 3, '20.00'),
(1300, 6, '40.00'),
(1300, 8, '50.00'),
(1300, 9, '50.00'),
(1400, 1, '30.00'),
(1400, 6, '50.00'),
(1400, 10, '50.00'),
(1400, 16, '75.00'),
(1400, 17, '75.00'),
(1500, 1, '30.00'),
(1500, 6, '75.00'),
(1500, 10, '55.00'),
(1500, 11, '55.00'),
(1600, 3, '20.00'),
(1600, 6, '40.00'),
(1600, 7, '45.00'),
(1600, 8, '45.00');

-- --------------------------------------------------------

--
-- Table structure for table `DEPARTMENT`
--

CREATE TABLE `DEPARTMENT` (
  `DepartmentName` char(35) NOT NULL,
  `BudgetCode` char(30) NOT NULL,
  `OfficeNumber` char(15) NOT NULL,
  `DepartmentPhone` char(12) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

--
-- Dumping data for table `DEPARTMENT`
--

INSERT INTO `DEPARTMENT` (`DepartmentName`, `BudgetCode`, `OfficeNumber`, `DepartmentPhone`) VALUES
('ACCOUNTING', 'BC-500-10', 'BLDG01-120', '360-285-8405'),
('ADMINISTRATION', 'BC-100-10', 'BLDG01-210', '360-285-8100'),
('FINANCE', 'BC-400-10', 'BLDG01-110', '360-285-8400'),
('HUMAN RESOURCES', 'BC-300-10', 'BLDG01-230', '360-285-8300'),
('INFOSYSTEMS', 'BC-700-10', 'BLDG02-210', '360-285-8600'),
('LEGAL', 'BC-200-10', 'BLDG01-220', '360-285-8200'),
('PRODUCTION', 'BC-900-10', 'BLDG02-110', '360-285-8800'),
('RESEARCH AND DEVELOPMENT', 'BC-800-10', 'BLDG02-250', '360-285-8700'),
('SALES AND MARKETING', 'BC-600-10', 'BLDG01-250', '360-285-8500');

-- --------------------------------------------------------

--
-- Table structure for table `EMPLOYEE`
--

CREATE TABLE `EMPLOYEE` (
  `EmployeeNumber` int(11) NOT NULL,
  `FirstName` char(25) NOT NULL,
  `LastName` char(25) NOT NULL,
  `Department` char(35) NOT NULL DEFAULT 'Human Resources',
  `Position` char(35) DEFAULT NULL,
  `Supervisor` int(11) DEFAULT NULL,
  `OfficePhone` char(12) DEFAULT NULL,
  `EmailAddress` varchar(100) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

--
-- Dumping data for table `EMPLOYEE`
--

INSERT INTO `EMPLOYEE` (`EmployeeNumber`, `FirstName`, `LastName`, `Department`, `Position`, `Supervisor`, `OfficePhone`, `EmailAddress`) VALUES
(1, 'MARY', 'JACOBS', 'ADMINISTRATION', 'CEO', NULL, '360-285-8110', 'MARY.JACOBS@WP.COM'),
(2, 'ROSALIE', 'JACKSON', 'ADMINISTRATION', 'ADMIN ASSISTANT', 1, '360-285-8120', 'ROSALIE.JACKSON@WP.COM'),
(3, 'RICHARD', 'BANDALONE', 'LEGAL', 'ATTORNEY', 1, '360-285-8210', 'RICHARD.BANDALONE@WP.COM'),
(4, 'GEORGE', 'SMITH', 'HUMAN RESOURCES', 'HR3', 1, '360-285-8310', 'GEORGE.SMITH@WP.COM'),
(5, 'ALAN', 'ADAMS', 'HUMAN RESOURCES', 'HR1', 4, '360-285-8320', 'ALAN.ADAMS@WP.COM'),
(6, 'KEN', 'EVANS', 'FINANCE', 'CFO', 1, '360-285-8410', 'KEN.EVANS@WP.COM'),
(7, 'MARY', 'ABERNATHY', 'FINANCE', 'FA3', 6, '360-285-8420', 'MARY.ABERNATHY@WP.COM'),
(8, 'TOM', 'CARUTHERS', 'ACCOUNTING', 'FA2', 6, '360-285-8430', 'TOM.CARUTHERS@WP.COM'),
(9, 'HEATHER', 'JONES', 'ACCOUNTING', 'FA2', 6, '360-285-8440', 'HEATHER.JONES@WP.COM'),
(10, 'KEN', 'NUMOTO', 'SALES AND MARKETING', 'SM3', 1, '360-285-8510', 'KEN.NUMOTO@WP.COM'),
(11, 'LINDA', 'GRANGER', 'SALES AND MARKETING', 'SM2', 10, '360-285-8520', 'LINDA.GRANGER@WP.COM'),
(12, 'JAMES', 'NESTOR', 'INFOSYSTEMS', 'CIO', 1, '360-285-8610', 'JAMES.NESTOR@WP.COM'),
(13, 'RICK', 'BROWN', 'INFOSYSTEMS', 'IS2', 12, NULL, 'RICK.BROWN@WP.COM'),
(14, 'MIKE', 'NGUYEN', 'RESEARCH AND DEVELOPMENT', 'CTO', 1, '360-285-8710', 'MIKE.NGUYEN@WP.COM'),
(15, 'JASON', 'SLEEMAN', 'RESEARCH AND DEVELOPMENT', 'RD3', 14, '360-285-8720', 'JASON.SLEEMAN@WP.COM'),
(16, 'MARY', 'SMITH', 'PRODUCTION', 'OPS3', 1, '360-285-8810', 'MARY.SMITH@WP.COM'),
(17, 'TOM', 'JACKSON', 'PRODUCTION', 'OPS2', 16, '360-285-8820', 'TOM.JACKSON@WP.COM'),
(18, 'GEORGE', 'JONES', 'PRODUCTION', 'OPS2', 17, '360-285-8830', 'GEORGE.JONES@WP.COM'),
(19, 'JULIA', 'HAYAKAWA', 'PRODUCTION', 'OPS1', 17, NULL, 'JULIA.HAYAKAWA@WP.COM'),
(20, 'SAM', 'STEWART', 'PRODUCTION', 'OPS1', 17, NULL, 'SAM.STEWART@WP.COM');

-- --------------------------------------------------------

--
-- Table structure for table `PROJECT`
--

CREATE TABLE `PROJECT` (
  `ProjectID` int(11) NOT NULL,
  `ProjectName` char(50) NOT NULL,
  `Department` char(35) NOT NULL,
  `MaxHours` decimal(8,2) NOT NULL DEFAULT 100.00,
  `StartDate` date DEFAULT NULL,
  `EndDate` date DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

--
-- Dumping data for table `PROJECT`
--

INSERT INTO `PROJECT` (`ProjectID`, `ProjectName`, `Department`, `MaxHours`, `StartDate`, `EndDate`) VALUES
(1000, '2017 Q3 PRODUCTION PLAN', 'PRODUCTION', '100.00', '2017-05-10', '2017-06-15'),
(1100, '2017 Q3 MARKETING PLAN', 'SALES AND MARKETING', '135.00', '2017-05-10', '2017-06-15'),
(1200, '2017 Q3 PORTFOLIO ANALYSIS', 'FINANCE', '120.00', '2017-07-10', '2017-07-25'),
(1300, '2017 Q3 TAX PREPARATION', 'ACCOUNTING', '145.00', '2017-08-10', '2017-10-15'),
(1400, '2017 Q3 PRODUCTION PLAN', 'PRODUCTION', '100.00', '2017-08-10', '2017-09-15'),
(1500, '2017 Q3 MARKETING PLAN', 'SALES AND MARKETING', '135.00', '2017-08-10', '2017-09-15'),
(1600, '2017 Q3 PORTFOLIO ANALYSIS', 'FINANCE', '140.00', '2017-10-05', NULL);

--
-- Indexes for dumped tables
--

--
-- Indexes for table `ASSIGNMENT`
--
ALTER TABLE `ASSIGNMENT`
  ADD PRIMARY KEY (`ProjectID`,`EmployeeNumber`),
  ADD KEY `ASSIGN_EMP_FK` (`EmployeeNumber`);

--
-- Indexes for table `DEPARTMENT`
--
ALTER TABLE `DEPARTMENT`
  ADD PRIMARY KEY (`DepartmentName`);

--
-- Indexes for table `EMPLOYEE`
--
ALTER TABLE `EMPLOYEE`
  ADD PRIMARY KEY (`EmployeeNumber`),
  ADD UNIQUE KEY `EmailAddress` (`EmailAddress`),
  ADD KEY `EMP_DEPART_FK` (`Department`),
  ADD KEY `EMP_SUPER_FK` (`Supervisor`);

--
-- Indexes for table `PROJECT`
--
ALTER TABLE `PROJECT`
  ADD PRIMARY KEY (`ProjectID`),
  ADD KEY `PROJ_DEPART_FK` (`Department`);

--
-- AUTO_INCREMENT for dumped tables
--

--
-- AUTO_INCREMENT for table `EMPLOYEE`
--
ALTER TABLE `EMPLOYEE`
  MODIFY `EmployeeNumber` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=21;

--
-- AUTO_INCREMENT for table `PROJECT`
--
ALTER TABLE `PROJECT`
  MODIFY `ProjectID` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=1601;

--
-- Constraints for dumped tables
--

--
-- Constraints for table `ASSIGNMENT`
--
ALTER TABLE `ASSIGNMENT`
  ADD CONSTRAINT `ASSIGN_EMP_FK` FOREIGN KEY (`EmployeeNumber`) REFERENCES `EMPLOYEE` (`EmployeeNumber`) ON DELETE NO ACTION ON UPDATE NO ACTION,
  ADD CONSTRAINT `ASSIGN_PROJ_FK` FOREIGN KEY (`ProjectID`) REFERENCES `PROJECT` (`ProjectID`) ON DELETE CASCADE ON UPDATE NO ACTION;

--
-- Constraints for table `EMPLOYEE`
--
ALTER TABLE `EMPLOYEE`
  ADD CONSTRAINT `EMP_DEPART_FK` FOREIGN KEY (`Department`) REFERENCES `DEPARTMENT` (`DepartmentName`) ON UPDATE CASCADE,
  ADD CONSTRAINT `EMP_SUPER_FK` FOREIGN KEY (`Supervisor`) REFERENCES `EMPLOYEE` (`EmployeeNumber`);

--
-- Constraints for table `PROJECT`
--
ALTER TABLE `PROJECT`
  ADD CONSTRAINT `PROJ_DEPART_FK` FOREIGN KEY (`Department`) REFERENCES `DEPARTMENT` (`DepartmentName`) ON UPDATE CASCADE;
COMMIT;

/*!40101 SET CHARACTER_SET_CLIENT=@OLD_CHARACTER_SET_CLIENT */;
/*!40101 SET CHARACTER_SET_RESULTS=@OLD_CHARACTER_SET_RESULTS */;
/*!40101 SET COLLATION_CONNECTION=@OLD_COLLATION_CONNECTION */;
